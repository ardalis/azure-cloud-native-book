---
title: Leveraging Containers and Orchestrators
description: Architecting Cloud Native .NET Apps for Azure | Leveraging Containers and Orchestrators
ms.date: 06/30/2019
---
# Leveraging Containers and Orchestrators

Docker is the most popular container management and imaging platform and allows you to quickly work with containers on Linux and Windows. Containers provide separate but reproducible application environments that will run the same way on any system. This makes them perfect for hosting and scaling applications and app components in cloud native applications. Containers are isolated from one another, so two containers on the same host hardware can have completely different versions of software and even operating system installed, without the dependencies causing conflicts.

What’s more, containers are completely defined by simple files that can be checked into source control. Unlike full servers, even virtual machines, which frequently require manual work to apply updates or install additional services, container infrastructure can easily be version-controlled. Thus, apps built to run in containers can developed, tested, and deployed using automated tools as part of a build pipeline.

Containers are immutable. Once you have a definition of a container, you can recreate that container and it will run exactly the same way. This immutability lends itself to component-based design. If some parts of an application don’t change as often as others, why redeploy the entire app when you can just deploy the parts that change most frequently? 

**TODO: Insert figure showing app broken into separate modules in separate containers**

Multi-tier architectures are nothing new, but with container-based applications it may make sense at a minimum to separate different tiers into separate containers, or to split an app into different containers based on features or cross-cutting concerns. However, by design containers only know about themselves. Once you need to deploy multiple containers that need to work together, you need something that can organize them and any shared dependencies they may have, such as network configuration. This is where orchestration tools come in to save the day!

**(insert figure showing cluster of containers designed to work together)**

Docker Desktop and VS Docker tooling

Kubernetes Minikube and Kubernetes Server from Docker Desktop



>[!div class="step-by-step"]
>[Previous](index.md)
>[Next](leveraging-serverless-functions.md)
