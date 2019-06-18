---
title: Centralized Configuration
description: Architecting Cloud Native .NET Apps for Azure | Centralized Configuration
ms.date: 06/30/2019
---
# Centralized Configuration

Cloud native applications involve many more running services than traditional single-instance monolithic apps. Managing configuration settings for dozens of interdependent services can be challenging, which is why centralized configuration stores are often implemented for distributed applications.

As discussed in [Chapter 1](introduction-to-cloud-native-applications.md), the 12 Factor App recommendations require strict separation between code and config. This means storing configuration settings as constants or literal values in code is a violation. This recommendation exists because the same code should be used across multiple environments, including development, testing, staging, and production. However, config values are likely to vary between each of these environments. Thus, config should be stored in the environment itself, or the environment should store the credentials to the centralized configuration store.

In reviewing the eShopOnContainers reference application, make note of where configuration values are stored and how they are provided to the app and its many independent services. A good example of a common configuration item that is shared across many services is the Application Insights instrumentation key. In many applications that use Application Insights, this key might be hard-coded in the web application's `Startup` class. Or perhaps found in its `appsettings.json` file. Although eShopOnContainers includes many different ASP.NET Core web applications, none of them store the instrumentation key in their project.

Instead, the projects expect the `ApplicationInsights__InstrumentationKey` environment variable to provide the key. However, with so many services running independently, it would be difficult to keep many different host machines' environment variables in sync. Fortunately, using Helm and Docker, the key is set in just one location, `./k8s/helm/inf.yaml`. Looking at this infrastructure configuration file, you'll see it also includes configuration information for common database connectivity, redis access information, message bus access, and miscellaneous application-wide settings. By combining environment variables and the ability to set container environment variables centrally using Helm, the application's configuration is easily managed from a single, central location.

- [eShopOnContainers inf.yaml file](https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/k8s/helm/inf.yaml)

>[!div class="step-by-step"]
>[Previous](hosting-the-eshoponcontainers-application.md)
>[Next](cloud-native-communication-patterns.md) <!-- Next Chapter -->
