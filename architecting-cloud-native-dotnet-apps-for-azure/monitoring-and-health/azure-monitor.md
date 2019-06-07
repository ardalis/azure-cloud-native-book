---
title: Azure Monitor
description: Architecting Cloud Native .NET Apps for Azure | Azure Monitor
ms.date: 06/30/2019
---

```
1.	What is Azure Monitor
2.	What does it collect (mention Application Insights)
3.	Working with dashboard, alerts, views and Power BI
4.	Azure Monitor for Containers Point to docs for most coverage; focus on what is important to consider for microservices/cloud native, like how to trace flow of a particular request through several microservices, for example
5.	Log Analytics
```

# Azure Monitor

No other cloud provider has as mature of a cloud application monitoring solution as that found in Azure. 
Gathering Logs and Metrics

## Reporting data

## Dashboards

There are several different dashboarding technologies which may be used to surface the information from Azure Monitor. Perhaps the simplest is to just run queries in Application Insights and plot the data into a chart. 
<<TODO SHOW EXAMPLE>>
These charts can then be embedded in the Azure portal proper through use of the dashboard feature. For users with more exating requirements such as being able to drill down into several tiers of data Azure Monitor data is available to PowerBI. PowerBI is an

## Alerts


>[!div class="step-by-step"]
>[Previous](logging.md)
>[Next](../index.md)
