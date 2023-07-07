---
title: "Microsoft Graph connectors overview"
description: "Use Microsoft Graph connectors to bring content from external services into Microsoft Graph, enabling external data to power Microsoft 365 intelligent experiences."
author: mecampos
ms.localizationpriority: high
doc_type: conceptualPageType
ms.prod: search
---

# Microsoft Graph connectors overview

[Microsoft 365](https://www.microsoft.com/microsoft-365) is a complete, intelligent solution that empowers users and organizations with innovative productivity experiences and rich insights to increase efficiency and drive business growth. Microsoft Graph is the data fabric that powers these intelligent experiences, and the [Microsoft Search API](graph/api/resources/indexing-api-overview) provides access to this data and intelligence.

Although most information workers spend much of their work time within productivity applications such as Microsoft 365, they also need a way to integrate that environment with the enterprise applications and other on-premises and SaaS cloud software and services that they use. Examples include enterprise resource planning (ERP) applications, customer resource management (CRM) applications, intranet applications, wikis, blogs, and social networking sites.

Microsoft Graph connectors offer an intuitive way to bring content from external services into Microsoft Graph, enabling external data to power Microsoft 365 intelligent experiences such as [Microsoft Search](microsoftsearch/connectors-overview).

Today, with Microsoft Graph connectors, the data you bring in from your organization can be discoverable in the following [experiences](connecting-external-content-experiences):
- [Microsoft Search](microsoftsearch/overview-microsoft-search) (GA)
- [Context IQ in Outlook Web](https://techcommunity.microsoft.com/t5/microsoft-365-blog/microsoft-editor-using-context-iq-in-outlook-on-the-web-and-word/ba-p/3643497) (GA)
- [Copilot](https://blogs.microsoft.com/blog/2023/03/16/introducing-microsoft-365-copilot-your-copilot-for-work/) (preview)
- [Microsoft 365 Hub](https://office.com) (formerly known as [Office.com](https://office.com)) (coming soon)

>[!NOTE]
>Microsoft Graph connectors for Microsoft 365 Copilot are in early access preview. For details about how to build a Microsoft Graph connetor that is integrated with Microsoft 365 Copilot, see [Copilot for Microsoft Graph connectors](connecting-external-content-experiences#Copilot). 

## Get started with custom connectors

The 100+ connectors currently available from Microsoft and partners enable you to connect to popular Microsoft and non-Microsoft services. Examples of existing connectors include Azure services, Box, ServiceNow, Salesforce, Google services, and MediaWiki.

To learn more about the existing Microsoft Graph connectors, visit the [Microsoft Graph connectors gallery](https://www.microsoft.com/microsoft-search/connectors/).

## Build a custom connector

While the existing connectors help connect to popular services, you might want to integrate with services that aren't available in the connectors gallery. You can use the Microsoft Graph connectors API to build custom connectors to bring your external data into Microsoft 365 experiences within your organization.

To get started, see the following:

- Learn about the set of [Graph connector experiences](connecting-external-content-experiences) where you want your custom connector data discoverable 
- [Build your first custom Microsoft Graph connector using APIs](connecting-external-content-build-quickstart.yml)
- [Build your first custom Microsoft Graph connector using the SDK](/graph/custom-connector-sdk-sample-overview)

## Next steps

* [Work with the Microsoft Graph connectors API](connecting-external-content-connectors-api-overview.md)
* [Use Postman with the Microsoft Graph connectors API](connecting-external-content-connectors-api-postman.md)
