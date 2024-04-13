+++
author = "Ian Crosby"
title = "Production Ready Ingress on Kubernetes"
date = "2018-02-07"
description = "Production Ready Ingress on Kubernetes"
categories = [
    "cloud",
]
featured = true
image = "danielle-macinnes-IuLgi9PWETU-unsplash.jpg"
+++

I recently had an interesting project building a proof of concept for a cloud based platform. The PoC is composed of a few services, a message queue and a couple simple UIs. All the pieces are containerized and deployed on Kubernetes (GKE).  As a final task before sending this over to the client, I needed to expose the front end publicly. What seemed like a straightforward task turned out to be a bit more time consuming, partially due to the specific requirements and partially due to an intricate technical complexity (typo in a config file). I learned quite a bit in the process so I thought I would share the steps I went through for anyone else who travels down this road.

Communication in Kubernetes
Inter service communication (within the Kubernetes cluster) comes out of the box. By leveraging the internal DNS we simply reference another service by name and our requests will be routed appropriately. This is an over simplification of course, but in most cases this just works. However, if we want to expose any of our applications to the outside world we require another solution. There are three main ways we can do this with Kubernetes:

Service Type NodePort - will expose our service on a port from a pre-configured range (default: 30000-32767) across each worker node.
Service Type LoadBalancer - will spin up a load balancer to front the service. This works only on supported cloud platforms (e.g. AWS, GCP, Azure).
Ingress - a collection of routing rules which are fulfilled by an Ingress Controller.
Ingress in a nutshell
Ingress is the most flexible and configurable of the three, so this is the solution we chose. It is comprised mainly of two pieces, the Ingress resource, which is a list of routing rules, and the Ingress controller, which is deployed in a pod (or pods) on the cluster and fulfills these rules. Ingress primarily deals with HTTP traffic, the rules are a combination of host and paths which map to an associated backend. In most cases you will run multiple instances of the ingress controller, and front them with a load balancer.

 
                                  |                      |
                                  |     Load Balancer    |
                                  |                      |
                                  +----------+-----------+
                                             |
                                             |
                                             |
+----------------------------------------+   |   +----------------------------------------+
|              Node 1                    |   |   |              Node 2                    |
|----------------------------------------|   |   |----------------------------------------|
|                    +----------------+  |   |   |                    +----------------+  |
|                    |                |  |   |   |                    |                |  |
|                    |   Ingress      |  |   |   |                    |   Ingress      |  |
|                    |  Controller    |------+   |                    |  Controller    |  |
|                    |                |  |       |                    |                |  |
|                    |                |  |       |                    |                |  |
|  +-------------+   +-------+--------+  |       |  +-------------+   +----------------+  |
|  |             |           |           |       |  |             |                       |
|  |             |           |           |       |  |             |                       |
|  |   App 1     |           |           |       |  |   App 2     |                       |
|  |             |-----------+           |       |  |             |                       |
|  |             |                       |       |  |             |                       |
|  +-------------+                       |       |  +-------------+                       |
+----------------------------------------+       +----------------------------------------+
	
*Not all Ingress Controllers are set up in the above manner.

Kubernetes Ingress has become quite mature and is relatively painless to setup at this point, however we had a few additional requirements which made the setup a bit more complex:

We had to support TLS
We wanted to protect the UI with Basic Authentication.
We needed websocket support.
Which Ingress Controller to Use?
As with many of the Kubernetes ‘add-ons’ there is no built-in Ingress controller. This allows us the freedom to choose among the various available implementations.

Since the cluster was on Google’s Container Engine (GKE) the default controller is Google’s L7, however we quickly found out that this does not support Basic Auth, so we then moved on to Nginx. Interestingly there are two (actually three) different nginx ingress controllers, one maintained by the Kubernetes community (kubernetes/ingress-nginx) and another by nginx themselves (nginxinc/kubernetes-ingress). There are some subtle differences between the controllers, here are a few of them I ran into:

Websockets requires adding an annotation when using the nginx (nginxinc) controller.
TCP/UDP connections can be handled by the nginx (kubernetes) controller by using a ConfigMap, not yet supported by others.
Authentication (Basic Auth, Digest) is not supported by the GCE controller.
Replacing the ingress path (rewrite-target) is only supported by the nginx (kubernetes) controller. (Note this is also supported by Traefik but with a different annotation)
A more complete view of the features supported by different controllers can be found here: https://github.com/kubernetes/ingress-nginx/blob/master/docs/annotations.md

DNS and TLS
Another requirement we had was to setup DNS to be able to expose our application on a subdomain of ours, and TLS so we could support https. For DNS, there is an interesting project currently in incubator (https://github.com/kubernetes-incubator/external-dns) which we looked into, but it was a bit overkill for our simple demo. Instead we simply manually created the managed zone within Google’s Cloud DNS and pointed it to the IP of our ingress load balancer.

As for TLS, this is quite easy to setup thanks to the kube-lego project (https://github.com/jetstack/kube-lego). Once deployed to your Kubernetes cluster, kube-lego creates a user account with LetsEncrypt, and will then create certificates for each Ingress resource marked with the proper annotation (kubernetes.io/tls-acme: "true").  Kube-lego is actually now in maintenance mode, and the recommended replacement is cert-manager (https://github.com/jetstack/cert-manager/).

WebSockets
The last requirement we needed to account for was that our front end we are exposing uses websockets. In general, websockets have become quite well supported by ingress controllers. Although I ran into a couple tricky pieces:

When using the nginx ingress controller (from Nginx) an annotation is required for services which require websocket support, while for the others (including the Kubernetes backed nginx ingress controller) no annotation is needed.
If the ingress controller is fronted with a Load Balancer we need to increase the response timeout for the backend (which defaults to 30 seconds).
Switching between Controllers
One complication which added a bit of frustration in going through this process is that switching between ingress controllers is not transparent. In addition to the specific features which may or may not be supported by different controllers as mentioned above, there are also discrepancies within features.

One example is how URL paths are handled. For example if I want to route everything under /foo/ path to service-a, (e.g. /foo/bar and /foo/baz). This is achieved differently in the GCE ingress controller (/foo/*) vs the Nginx ingress controller (/foo/). There is an open issue (https://github.com/kubernetes/ingress-nginx/issues/555) to standardise or document the different implementations.

These differences can be a bit frustrating, it’s best to determine your ingress requirements up front and find the controller which satisfies those. Ideally there will be some standardization around ingress controllers so that swapping out one for another would be seamless.

Conclusion
Exposing applications outside of a cluster is a very common use case. There are several ways to go about this, with ingress being the most flexible. The implementation (the ingress controller) is not standardized, leaving us with several options. On the one hand this is great because it allows us the freedom to choose the tool/technology that fits best, but the lack of consistency can make setting things up more challenging than it needs to be.

That being said, all the necessary pieces to properly expose applications from your cluster to the outside world are available, thanks to projects like External-DNS and kube-lego/cert-manager. This is a testament to the Kubernetes community which is the most active open source community at the moment. When a need arises it is soon filled (possibly by multiple projects). It will be interesting to watch this space to see how it evolves, with new tools such as Istio (https://istio.io/docs/tasks/traffic-management/ingress.html) offering more complete solutions to Kubernetes traffic management.

