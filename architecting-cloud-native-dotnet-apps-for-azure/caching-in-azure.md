---
title: Caching in Azure
description: Architecting Cloud Native .NET Apps for Azure | Caching in Azure
ms.date: 06/30/2019
---
# Caching in Azure

Blah

Microservice systems typically use a combination of these interaction types when executing operations that require cross-service interaction. Let’s take a close look at each and how you might implement them.

## Redis Cache

<https://redislabs.com/partner/microsoft/>

Often, one microservice may have the need to *query* another, requiring an immediate response in order to complete an operation. For example, a shopping basket microservice may need product information and a price in order to add an item to its basket. There are a number of approaches for implementing query operations.

## Azure CDN

Sometimes, a microservice may require another microservice to perform an action. For example, the Ordering microservice may need the Shipping microservice to create a shipment for an approved order. Often called a *command message*, the microservice invoking the action, called a Producer, makes a command to another service, the Consumer, by sending it a message as shown below in Figure x.

## Summary

Blah, blah, blah

>[!div class="step-by-step"]
>[Previous](azure-data-storage.md)
>[Next](resiliency.md) <!-- Next Chapter -->
