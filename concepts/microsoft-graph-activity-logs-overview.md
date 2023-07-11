---
title: "Access Microsoft Graph activity logs (preview)"
description: "."
author: "FaithOmbongi"
ms.reviewer: yiheguo
ms.localizationpriority: high
ms.prod: "applications"
doc_type: conceptualPageType
ms.date: 07/11/2023
---

# Access Microsoft Graph activity logs (preview)

**Microsoft Graph activity logs** are an audit trail of all HTTP requests that the Microsoft Graph service received and processed for a tenant. The logs are stored in Azure Monitor Logs and tenant administrators can analyze them through the Log Analytics interface. Tenant admins can also configure exports to destinations like Azure Storage for long-term storage or use Azure Event Hubs to export to external SIEM tools for alerting, analysis, or archival.

Only logs for API requests made from line of business applications, API clients, and SDKs are available but not API requests made by Microsoft applications like Outlook, Teams, or the Entra portal.

## Prerequisites

To access the Microsoft Graph activity logs, you need the appropriate privileges.

- An Azure subscription to access the storage destination resources.
  - [Required] An Azure Monitor Log Analytics workspace in your Azure subscription
  - To stream to an alternative description, you need an Azure Storage Account or Azure Event Hubs namespace.
- An Azure AD Premium P1 or P2 tenant license in your tenant.
- A user with one of the following Azure AD administrator roles listed in the order of least to most privileged role.
  - Security Reader - To read the logs
  - Global Reader - To read the logs
  - Security Administrator – To configure diagnostic settings and read the logs
  - Global Administrator – To configure diagnostic settings and read the logs
- Understand how to send logs to a Log Analytics workspace. For more information, see [Stream logs to Azure Monitor](/azure/active-directory/reports-monitoring/howto-integrate-activity-logs-with-log-analytics).

## What data is available in the Microsoft Graph activity logs?

The following data relating to API requests is available for Microsoft Graph activity logs on the Logs Analytics interface.

<!--To use CRR to avoid duplication once the API Doctor link validation is fixed. -->

| Column | Type | Description |
|--|--|--|
| AadTenantId | String | The Azure AD tenant ID. |
| ApiVersion | String | The API version of the event. |
| AppId | String | The identifier for the application. |
| _BilledSize | real |  |
| ClientRequestId | String | Optional. The client request identifier when sent. If no client request identifier is sent, the value is equal to the operation identifier. |
| DurationMs | Int | The duration of the request in milliseconds. |
| IpAddress | String | The IP address of the client from where the request occurred. |
| _IsBillable | String |  |
| Location | String | The name of the region that served the request. |
| OperationId | String | The identifier for the batch. For nonbatched requests, this value is unique per request. For batched requests, this value is the same for all requests in the batch. |
| RequestId | String | The identifier representing the request. |
| RequestMethod | String | The HTTP method of the event. |
| RequestUri | String | The URI of the request. |
| ResponseSizeBytes | Int | The size of the response in Bytes. |
| ResponseStatusCode | Int | The HTTP response status code for the event. |
| Roles | String | The roles in token claims. |
| Scopes | String | The scopes in token claims. |
| ServicePrincipalId | String | The identifier of the servicePrincipal making the request. |
| SignInActivityId | String | The identifier representing the sign-in activities. |
| SourceSystem | String | The type of agent that collected the event. For example, *OpsManager* for Windows agent, either direct connect or Operations Manager, *Linux* for all Linux agents, or *Azure* for Azure Diagnostics. |
| TenantId | String | The Log Analytics workspace ID. |
| TimeGenerated | Datetime | The date and time the request was received. |
| TokenIssuedAt | Datetime | The timestamp the token was issued at. |
| Type | String | The name of the table |
| UserAgent | String | The user agent information related to request. |
| UserId | String | The identifier of the user making the request. |

## Sample audit scenarios for Microsoft Graph activity logs

- To get full visibility into the transactions made by line of business apps and other API clients that you have consented to in the tenant.
- To analyze client app behavior that led to throttling.
- To investigate requests that a compromised user or app made in yout tenant.
- Query for anomalous API request behavior by a client application or user​.
- To discover the actual requests made by a user or app and correlate the information with sign in or directory audit logs.
- To discover the permissions that a calling app was granted when they initiated a request.
- To trigger alerts in Azure Monitor Log Analytics based on signals and patterns in the logs.

## Configure to receive the Microsoft Graph activity logs

You can configure to stream the logs through either the Entra portal or the Azure Resource Manager APIs. For more information, see the guidance in the following articles.

- [Integrate activity logs with Azure Monitor logs](/azure/active-directory/reports-monitoring/howto-integrate-activity-logs-with-log-analytics)
- [Configure diagnosticSettings through the ARM API](/azure/templates/microsoft.insights/diagnosticsettings?pivots=deployment-language-arm-template)

## Cost planning estimates

If you already have an Azure AD P1 license, you need an Azure subscription to set up the storage account, Log Analytics workspace, or Event Hubs. The Azure subscription comes at no cost, but you have to pay to utilize Azure resources. These resources could include the storage account that you use for archival and the Event Hubs that you use for streaming.

The amount of data logged and, thus, the cost incurred, can vary significantly depending on the tenant size and the applications your organization is using that interact with Microsoft Graph APIs. These estimations should be used for general consideration only.

### Azure Storage size and cost estimates for Microsoft Graph activity logs

A Microsoft Graph activity log event uses about 1 KB of data storage. For a tenant with 100,000 users, which would incur about 1.5 million events per day, you would need about 1.4 GB of data storage per day. Because writes occur in approximately five-minute batches, you can anticipate around 9,000 write operations per month.

The following table contains a cost estimate in USD of, depending on the size of the tenant, a general-purpose v2 storage account in West US for at least one year of retention. To create a more accurate estimate for the data volume that you anticipate for your application, use the [Azure storage pricing calculator](https://azure.microsoft.com/en-us/pricing/details/storage/blobs/).

| Number of users | Events per day | Volume of data per month | Cost per month | Cost per year |
|-----------------|----------------|--------------------------|----------------|---------------|
| 1,000           | 500,000        | 14 GB                    | $0.30          | $3.62         |
| 100,000         | 40M            | 1 TB                     | $18.48         | $221.78       |

### Event Hubs messages and cost estimates for Microsoft Graph activity logs

Events are batched into approximately five-minute intervals and sent as a single message that contains all the events within that timeframe. A message in the Event Hubs has a maximum size of 256 KB. If the total size of all the messages within the timeframe exceeds that volume, multiple messages are sent.
For example, about 400-500 events per second might occur for a large tenant of more than 100,000 users, a rate that equates to roughly 140,000 events every five minutes. Microsoft Graph Activity logs are about 1 KB per event, which equates to 136 MB of data. Therefore, 545 messages are sent to the event hub in that five-minute interval. 

The following table contains estimated costs per month for a basic event hub in West US. The volume of event data can vary from tenant to tenant, based on factors like user Microsoft 365 application usage. To calculate an accurate estimate of the data volume that you anticipate for your application, use the [Event Hubs pricing calculator](https://azure.microsoft.com/pricing/details/event-hubs/).

| Number of users | Events per second | Events per five minutes | Volume per interval | Message per month | Cost per month |
|--|--|--|--|--|--|
| 1,000 | 6 | 1,800 | 1.8 MB | 62,000 | $10.8 |
| 100,000 | 460 | 140,000 | 1.33 MB | 4,800,000 | $10.94 |

### Azure Monitor Logs cost estimates for Microsoft Graph activity logs

| Number of users | Events per day | Events per month (30 days) | Cost per month in USD (est.) |
|--|--|--|-:|
| 1,000 | 500,000 | 15 million | As Basic logs: $6.60 <br/> As Analytics Logs: $29.61 <br/> Monthly Retention: $1.29 |
| 100,000 | 40,000,000 | 1.2 billion | As Basic logs: $527.86 <br/> As Analytics Logs: $2,368.93 <br/> Monthly Retention: $103.00 |

To review costs related to managing the Azure Monitor logs, see [Azure Monitor Logs pricing details](/azure/azure-monitor/logs/cost-logs#pricing-model).

## Latency expectations

The latency is measured from the time the Microsoft Graph request is made to the time it's available in the Azure Monitor logs. 95th percentile latency for Microsoft Graph activity logs is approximately two minutes while the 99th percentile latency is approximately five minutes.

## Azure Monitor Logs query examples

If you send Microsoft Graph Activity Logs to a Log Analytics workspace, you can build queries for the logs in Kusto Query Language (KQL). For more information about queries in Azure Monitor Logs, see [Log queries in Azure Monitor](/azure/azure-monitor/logs/log-query-overview). You can use these queries for data exploration, to build alert rules, build Azure dashboards, or integrate into your custom applications using the Azure Monitor Logs API or Query SDK.

The following Kusto query identifies high numbers of requests to /users APIs by app and principal.

```kusto
MicrosoftGraphActivity
| where TimeGenerated >= ago(2h)
| where RequestUri contains "/users"
| summarize NumRequests=count(RequestId) by appId, servicePrincipalId, UserId
| Sort by NumRequests desc
| limit 20
```

The following Kusto query counts failed requests to different Groups entities by app and principals.

```kusto
MicrosoftGraphActivity
| where TimeGenerated >= ago(2h)
| where ResponseStatusCode==403
| where RequestUri contains "/groups"
| summarize UniqueRequests=count_distinct(RequestId) by appId, servicePrincipalId, UserId
| Sort by UniqueRequests desc
| limit 20
```

## Join Microsoft Graph activity logs and other audit logs

In the Logs Analytics interface, you can correlate the Microsoft Graph activity logs and other logs like sign-in logs and Azure AD activity reports. For example, you can join the Microsoft Graph activity logs with Azure AD activity reports to identify the user who made the request. The following query joins the Microsoft Graph activity logs with Azure AD audit logs to identify the user who made the request.


## Limitations

Some Microsoft Graph services communicate with other Microsoft services through Microsoft Graph APIs
for background data reads or writes. Currently, the Microsoft Graph activity logs include logs for all
requests to Microsoft Graph APIs for resources in your tenant. While the Microsoft Graph activity logs give you insights into the use of Microsoft Graph APIs in your tenant, we recommend using Azure AD and Microsoft 365 audit logs to analyze changes to tracked resources in your tenant, regardless of the source of the request.

## See also

- [Azure Monitor Reference: MicrosoftGraphActivityLogs](/azure/azure-monitor/reference/tables/microsoftgraphactivitylogs)
- [Stream data from Azure Monitor to an event hub or external partner](/azure/azure-monitor/essentials/stream-monitoring-data-event-hubs)
