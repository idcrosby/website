+++
author = "Ian Crosby"
title = "Weather Predictions Straight from the Cloud"
date = "2016-02-16"
description = "Weather Predictions Straight from the Cloud"
categories = [
    "cloud",
]
featured = true
image = "danielle-macinnes-IuLgi9PWETU-unsplash.jpg"
+++

Can a fleet of customized drones improve your daily commute? We recently connected with the Swiss meteorological gurus at Meteomatics who have developed specialized drones to collect and transmit weather data. We teamed up with them to find out the benefits of their new technology and what sort of issues it might be able to solve.

The Problem
Why is it that weather predictions, as we can all attest to, are so unreliable? If we look at traditional weather data collection, we either have ground based sensors and weather stations, or high altitude ones such as satellites, radar, and weather balloons. This leaves a gap in the data - we have little or no values between ground level to nearly 1.5 kilometers above the earth, in what is known as the Planetary Boundary Layer.

Drones to the rescue
Weather Predictions Straight from the Cloud

Drones offer an attractive option to fill this gap. They are relatively cheap compared to other weather data collecting technologies, and reusable (unlike weather balloons which are launched once and lost somewhere up in the mesosphere). So Meteomatics set out to do just that, they have developed “Meteodrones”, which collect various weather data (temperature, humidity, wind speed, pressure, etc) and relay this information back to a ground station.

Bigger Data
After some initial flights and data collection, Meteomatics ingested this new data into their existing weather algorithms. They quickly realized that this new data gave some interesting insights and they were able to greatly improve the accuracy of their predictions of certain weather conditions, such as thunderstorms and fog. As the number of drones and flights increases, so does the data, resulting in accurate, localised microforecasts.

Enter Mantl
IoT, big data, drones! This was too great an opportunity to pass up.  We jumped on the chance to build a really cool microservices application to help show off Mantl.  We opted for one of the potential use cases this new weather data offers us: localized fog predictions for planning a trip. Using Mantl to deploy the application meant we got a lot of piecess ‘out of the box’ that we didn’t need to build or integrate ourselves. Along with the benefits of Mesos and Marathon for fault tolerance and high availability, we have Consul integrated for service discovery, Traefik for load balancing, as well as Logstash and Elasticsearch for ingesting and storing our data.

This diagram shows the overall architecture of our application within Mantl, and how are services interact.

Weather Drone Application Architecture diagram

The following two videos show off the finished demo application we created for CiscoLive in Berlin. This first video shows the front end and discusses some of the technologies we used to create our application:


This second video goes into the details of the infrastructure and shows the resiliency of the services.


Working with Meteomatics to take advantage of their new drones and the insight the data gives allowed us to play with some really cool technologies while also creating a useful and interesting application. By leveraging the Mantl platform, and the tools which come with it, we were able to quickly go from local demo application to a cloud deployed, highly available, fault tolerant microservice application. Within a very short time we were able to come away with a pretty cool result, and there is plenty of potential for us to continue to build on.