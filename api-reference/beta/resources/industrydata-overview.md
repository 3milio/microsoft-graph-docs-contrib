---
title: "Use the industry data API as an extract, transform, and load (ETL) engine (preview)"
description: "The industry data API is a multi-vertical, cross-industry, ETL (Extract-Transform-Load) platform that combines data from multiple sources into a single Azure Data Lake data store, normalizes the data, and exports it in outbound flows."
author: "mlafleur"
ms.localizationpriority: medium
ms.prod: "industry-data-etl"
doc_type: conceptual
---

# Use the industry data API as an extract, transform, and load (ETL) engine (preview)

Namespace: microsoft.graph.industryData

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

The industry data API is a multi-vertical, cross-industry, ETL (Extract-Transform-Load) platform that combines data from multiple sources into a single Azure Data Lake data store, normalizes the data, and exports it in outbound flows. In the current release, the API is highly tailored to the education industry.

The API provides resources that you can use to get statistics after the data is processed, and assist with monitoring and troubleshooting.

## Overview of application in education

In the current release, the industry data API is highly tailored to the education industry, powering the [Microsoft School Data Sync](https://sds.microsoft.com) (SDS) platform to help automate the process of importing data and synchronizing organizations, users and users associations, and groups <!-- with Azure Active Directory (Azure AD) and Office 365 --> from student information systems (SIS) and student management systems (SMS) into the Azure Data Lake of an organization. After normalizing the data in Azure Data Lake, it utilizes the data in multiple outbound flows, synchronizing data with [Insights for Education Leaders](https://support.microsoft.com/topic/leader-s-guide-to-education-insights-premium-8738d1b1-4e1c-49bd-9e8d-b5292474c347) and [Education Data Lake Export](/schooldatasync/enable-education-data-lake-export) for custom analytics scenarios.

![Conceptual view of the industry data ETL process](/graph/images/industrydata-overview.png)

First, connect to the data of your institution. Define an inbound flow: Create [sourceSystemDefinition](industrydata-sourcesystemdefinition.md), [dataConnector](industrydata-industrydataconnector.md), and [yearTimePeriodDefinition](industrydata-yeartimeperioddefinition.md). By default, the inbound flow activates twice (2x) daily (called a _run_).

When the run starts, it connects to the **sourceSystemDefinition** and **dataConnector** of the inbound flow, and performs basic validation. Basic validation ensures that the connection is correct, for [OneRoster API](https://www.imsglobal.org/activity/onerosterlis) as a source, or the filenames and headers are correct for CSV as a source.

Next, the system transforms the data for import in preparation for advanced validation. As part of the data transformation, the data is associated based on the configured **yearTimePeriodDefinition**.

The system stores then the latest copy of the Azure Active Directory (Azure AD) of the tenant into the Azure Data Lake. The copy of the Azure AD assists with user matching between the **sourceSystemDefinition** and the Azure AD user object. At this stage, the match link is written only to the Azure Data Lake.

Next, the inbound flow performs advanced validation to determine data health. The validation focuses on identifying errors and/or warnings. Validation follows the concept of bringing in good data and keeping out bad data.

- Errors mean that a record didn't pass validation and was removed from further processing.
- Warnings mean that the value on an optional field of a record didn't pass. The value was removed from the record, however, the record was included for further processing.

Errors and warnings are used to help better understand data health.

For the data that passed validation, the process uses the configured **yearTimePeriodDefinition** to determine its association for longitudinal storage.

- As the data is stored the internal representation in the Azure Data Lake of the tenant, it identifies when it was first seen by industry data.
- For data linked with a user organization, role association, and group association, it also identifies data as active in session based on the **yearTimePeriodDefinition**.
- In future runs, for the same inbound flow, **sourceSystemDefinition**, and **yearTimePeriodDefinition**, industry data identifies if the record is still seen.
- Based on the presence or absence of record, the record is kept active or marked as no longer active in session for the configured **yearTimePeriodDefinition**. This process determines the historical and longitudinal nature of the data between days, months, and years.

At the end of each run, [industryDataRunStatistics](industrydata-industrydatarunstatistics.md) are available to determine data health.

- Error and warnings related to **industryDataRunStatistics** are produced to help provide an initial understanding of data health.
- When you investigate data health, industry data provides the ability to download a log file that contains information based on the errors and warnings found to begin the data investigation process to correct the data in the source system.

After investigating and addressing any data errors and/or warnings, or are comfortable with the current state of the data health, then you can enable the scenarios with the data that is now in the education data lake. When you enable a scenario to use this data, the scenario creates an outbound flow. <!-- Outbound flows are defined by Microsoft 365 provisioning, Insights & Analytics. -->

<!-- Microsoft 365 Provisioning outbound flows help with simplifying management of users and classes. Only active and matched users are included in the data that will be used to write the link to the AAD user object between the SIS/ SMS and their sections for groups and Teams classrooms. -->

Insights and analytics help provide analysis for student progress and activity within their classes. Guided by this data, educators have the information they need to ensure that their students' emotional, social, and academic needs are being met.

For more information, see the sections School Data Sync, SDS prerequisites, and SDS core concepts of the [School Data Sync Overview](/schooldatasync/school-data-sync-overview) on the platform and architecture.

## Registration, permissions, and authorization

You can integrate industry data APIs with 3rd-party apps. To enable this integration, we recommend taking time to review the following articles.

- To explore the basics documentation, see [Authentication and authorization basics](/graph/auth/auth-concepts).
- To learn how to add and register an application, see [Register an application with the Microsoft identity platform](/graph/auth-register-app-v2).
- To read and write resources on behalf of a user, see [Get access on behalf of a user](/graph/auth-v2-user).
- For permissions via a consent process, see [Microsoft Graph permissions reference](/graph/permissions-reference).
- For steps to resolve common errors, see [Resolve Microsoft Graph authorization errors](/graph/resolve-auth-errors).

## Common use cases

| Use cases                                                   | REST resources                                                                | See also                                                                                         |
| :---------------------------------------------------------- | :---------------------------------------------------------------------------- | :----------------------------------------------------------------------------------------------- |
| Create an activity to import a delimited data set          | [inboundFileFlow](../resources/industrydata-inboundfileflow.md)               | [Methods of inboundFileFlow](../resources/industrydata-inboundfileflow.md#methods)               |
| Create a connector to retrieve data from an Azure Data Lake | [azureDataLakeConnector](../resources/industrydata-azuredatalakeconnector.md) | [Methods of azureDataLakeConnector](../resources/industrydata-azuredatalakeconnector.md#methods) |
| Define a source of inbound data                             | [sourceSystemDefinition](../resources/industrydata-sourcesystemdefinition.md) | [Methods of sourceSystemDefinition](../resources/industrydata-sourcesystemdefinition.md#methods) |

## Concepts

Industry data APIs power School Data Sync which is a data transformation engine. It imports data sets from external sources (SIS/SMS), transforms the data into a common data model, and writes the transformed data to various external services, like users and groups to Azure AD, and ability to create a team based group.

The following articles are to help with some basics that are specific to industry data APIs.

### Data domain

The **dataDomain** property defines the type of data that is imported and determines the common data model format for it to be stored in. Currently, the only supported **dataDomain** is `educationRostering`.

### Reference definitions

A [referenceDefinition](industrydata-referencedefinition.md) represents an enumerated value. Each supported industry domain receives a distinct collection of definitions. **referenceDefinition** resources are used extensively throughout the system, both for configuration and transformation, where the potential values are specific to a given industry. Each **referenceDefinition** uses a composite identifier of `{referenceType}-{code}` to provide a consistent experience across customer tenants.

#### Reference values

Types based on [referenceValue](industrydata-referencevalue.md) provide a simplified developer experience for binding **referenceDefinition** resources. Each **referenceValue** type is bound to a single reference type, allowing developers to provide only the **code** portion of the referencing definition as a simple string and eliminating potential confusion as to which type of **referenceDefinition** a given property is expected.

#### Example usage

The **userMatchingSettings.sourceIdentifier** property takes a [identifierTypeReferenceValue](industrydata-identifiertypereferencevalue.md) type that binds to the `RefIdentifierType` **referenceType**.

```json
"sourceIdentifier": {
    "code": "username"
},
```

A **referenceDefinition** might also be bound directly using the **value** property.

```json
"sourceIdentifier": {
    "value@odata.bind": "external/industryData/referenceDefinitions/RefIdentifierType-username"
},
```

### Role groups

Transformation of the data is often shaped by each individual user's role within an organization. These roles are defined as reference definitions. Given the number of potential roles, binding each role individual would result in a tedious user experience. [Role groups](industrydata-rolegroup.md) are simply a collection of `RefRole` codes.

```json
{
  "@odata.type": "#microsoft.graph.industryDataRoleGroup",
  "id": "37a9781b-db61-4a3c-a3c1-8cba92c9998e",
  "displayName": "Staff",
  "roles": [
    { "code": "adjunct" },
    { "code": "administrator" },
    { "code": "advisor" },
    { "code": "affiliate" },
    { "code": "aide" },
    { "code": "alumni" },
    { "code": "assistant" }
  ]
}
```

### Industry data connectors

An [industryDataConnector](industrydata-industrydataconnector.md) acts as a bridge between a [sourceSystemDefinition](industrydata-sourcesystemdefinition.md) and an [inboundFlow](industrydata-inboundflow.md). It is responsible for acquiring data from an external source and providing the data to inbound data flows.

#### Upload and validate CSV data

For more information:

- [Data Ingestion with SDS v2.1 CSV](/schooldatasync/data-ingestion-with-sds-v2.1-csv)
- [SDS V2.1 CSV File Format](/schooldatasync/sds-v2.1-csv-file-format):
  - File names and column headers are case-sensitive.
  - CSV files must be in UTF-8 format.
  - No line breaks in incoming data.
  - To review and download sample set of SDS V2.1 CSV files, see the [SDS GitHub repository](https://github.com/OfficeDev/O365-EDU-Tools/tree/master/CSV%20Samples).

> [!IMPORTANT]
> The [industryDataConnector](industrydata-industrydataconnector.md) doesn't accept delta changes so each upload session must contain the complete data set. Supplying only partial or delta data results in the transition of any missing records to an inactive state.

##### Request an upload session

The [azureDataLakeConnector](industrydata-azuredatalakeconnector.md) uses CSV files uploaded to a secure container. This container lives within the context of a single [fileUploadSession](industrydata-fileuploadsession.md) and is automatically destroyed after data validation or the file upload session expires.

The current file upload session is retrieved from an **azureDataLakeConnector** via the [getUploadSession](../api/industrydata-azuredatalakeconnector-getuploadsession.md) that returns the SAS URL for uploading the CSV files.

##### Validate uploaded files

Uploaded data files must be validated before an inbound flow can process the data. The validation process finalizes the current **fileUploadSession** and verifies that all required files are present and properly. Validation is initiated by calling the [industryDataConnector: validate](../api/industrydata-industrydataconnector-validate.md) action of the **azureDataLakeConnector**.

The **validate** action creates a long-running [fileValidateOperation](industrydata-filevalidateoperation.md). The URI for the **fileValidateOperation** is provided in the `Location` header of the response. You can use this URI to track the status of the long-running operation, and once complete, any errors or warnings encountered during validation.

## What's new

Find out about the [latest new features and updates](/graph/whats-new-overview) for this API set.

## Next steps

Use the Microsoft Graph industry data APIs as an extract, transform, and load (ETL) engine. To learn more:

- Explore the resources and methods that are most helpful to your scenario.
- Try the API in the [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer).

## See also

[Overview of the industry data API in Microsoft Graph](/graph/industrydata-concept-overview)
