---
title: Leveraging Serverless Functions
description: Architecting Cloud Native .NET Apps for Azure | Leveraging Serverless Functions
ms.date: 06/30/2019
---
# Leveraging Serverless Functions

In the spectrum of managing full machines and operating systems to leveraging cloud capabilities, serverless lives at the extreme end where the only thing you're responsible for is your code, and you only pay for your code when it runs. Azure Functions provide a way to build serverless capabilities into your applications. Traditionally, Azure Functions were built on the Azure platform or on infrastructure running the Azure Stack or the Azure Functions Runtime. However, you can also run Azure Functions within a Docker container for additional portability and flexibility. Adding support for docker to an Azure Functions project is as simple as adding a switch to the command line:

```cli
func init ProjectName --docker
```

When creating an Azure Function, you must choose the programming language you want to use from these options:

- dotnet (C#)
- node (JavaScript)
- python

When the project is created, it will include a Dockerfile. Next, you can create and test your function locally. [See this tutorial](https://docs.microsoft.com/azure/azure-functions/functions-create-function-linux-custom-image) for detailed steps to get started building Azure Functions with Docker support.

Azure Functions are well-suited to cross-functional communication. If you have multiple applications or microservices running in separate containers or servers and communicating using messaging, Azure Functions are an ideal solution to handling inter-process messages. Azure offers a variety of ways to send messages between services, such as storage queues and Azure Service Bus. Azure functions can be written to respond to new messages as well as to send messages over these services. Ideally, Azure functions should be short-lived and stateless. Since the function is self-contained, you're responsible for performing any necessarily exception handling and retry logic within the function, too. For performance reasons, if it's possible your event source may be receiving many small messages, it's best to process incoming messages in batches, rather than individually.

## References

- [Create a function on Linux using a custom image](https://docs.microsoft.com/azure/azure-functions/functions-create-function-linux-custom-image)
- [Azure Functions Best Practices](https://docs.microsoft.com/azure/azure-functions/functions-best-practices)

>[!div class="step-by-step"]
>[Previous](leveraging-containers-and-orchestrators.md)
>[Next](combining-containers-and-serverless-approaches.md)
