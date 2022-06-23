---
title: "Add custom properties to resources using extensions"
description: "Microsoft Graph provides a single API endpoint that gives you access to rich people-centric data and insights through resources such as user and message. You can also extend Microsoft Graph with your own application data using extensions."
author: "dkershaw10"
ms.localizationpriority: high
ms.custom: graphiamtop20
---

# Add custom properties to resources using extensions

Microsoft Graph provides a single API endpoint to access rich people-centric data and insights through resources such as [user](/graph/api/resources/user) and [message](/graph/api/resources/message). You can also extend Microsoft Graph with your own application data by adding custom properties to store data in Microsoft Graph resources without requiring an external data store.

In this article, we'll discuss how Microsoft Graph supports adding data to its resources, the options available to add custom properties and when to use them.

> [!IMPORTANT]
> Do not use extensions to store sensitive personally identifiable information, such as account credentials, government identification numbers, cardholder data, financial account data, healthcare information, or sensitive background information.

## Why add custom properties to Microsoft Graph?

* As an ISV developer, you might decide to keep your app lightweight and store app-specific user profile data in Microsoft Graph by extending the **user** resource.
* Alternatively, you might want to retain your app’s existing user profile store, and add an app-specific identifier to the **user** resource.
* As an enterprise developer, the in-house applications that you build might rely on your organization's HR-specific data. Integration within multiple applications can be simplified by storing this data in custom properties in Microsoft Graph.

## Custom property options in Microsoft Graph

Microsoft Graph offers four types of extensions for adding custom properties.

1. Extension attributes properties
2. Directory (Azure AD) extensions
3. Schema extensions
4. Open extensions

### 1. Extension attributes properties

Azure AD offers a set of 15 custom properties with predefined names on the [user](/graph/api/resources/onpremisesextensionattributes) and [device](/graph/api/resources/onpremisesextensionattributes) resources. These properties were initially custom attributes provided in on-premises Active Directory (AD) and Microsoft Exchange. However, they can now be used for more than syncing on-premises AD and Microsoft Exchange data to Azure AD through Microsoft Graph.

You can use the extension attributes 1-15 to store up to 15 string values on a **user** or **device** resource instance, through the **onPremisesExtensionAttributes** and **extensionAttributes** properties respectively. The values may be assigned using a POST operation to create an instance of the resource, or updated with a PATCH operation to the resource instance. They can also be filtered.

#### Developer experience

The following example shows how the data in extension attributes 1-15 is presented on the user resource instance.

##### Request

```msgraph-interactive
GET https://graph.microsoft.com/v1.0/users?$select=id,displayName,onPremisesExtensionAttributes
```

##### Response

```http
{
    "@odata.context": "https://graph.microsoft.com/v1.0/$metadata#users(id,displayName,onPremisesExtensionAttributes)",
    "value": [
        {
            "id": "071cc716-8147-4397-a5ba-b2105951cc0b",
            "displayName": "Adele Vance",
            "onPremisesExtensionAttributes": {
                "extensionAttribute1": "Contractor",
                "extensionAttribute2": "50",
                "extensionAttribute3": null,
                "extensionAttribute4": "1478354",
                "extensionAttribute5": "10239390",
                "extensionAttribute6": null,
                "extensionAttribute7": null,
                "extensionAttribute8": null,
                "extensionAttribute9": null,
                "extensionAttribute10": "11",
                "extensionAttribute11": null,
                "extensionAttribute12": "/o=ExchangeLabs/ou=Exchange Administrative Group (FYDIBOHF47SPDLT)/cn=Recipients/cn=5ee781fc7egc7aa0b9394bddb44e7f04-Adele Vance",
                "extensionAttribute13": null,
                "extensionAttribute14": null,
                "extensionAttribute15": null
            }
        }
    ]
}
```

### 2. Directory (Azure AD) extensions

[Directory extensions](/graph/api/resources/extensionProperty) provide developers with a strongly typed, discoverable and filterable extension experience for directory objects.

Directory extensions are first registered on an application through the [Create extensionProperty](/graph/api/application-post-extensionproperty) operation and must be explicitly targeted to specific directory objects. After the application has been consented to by a user or an admin, the extension properties become immediately accessible in the tenant. All authorized applications in the tenant can read and write data on any extension properties defined on an instance of the target directory object.

For the list of resource types that can be specified as target objects for a directory extension, see [Choose an extension type for your application](#choose-an-extension-type-for-your-application).

#### Developer experience

Directory extensions are managed through the [extensionProperty](/graph/api/resources/extensionproperty) resource and its associated methods. The data is managed through the same REST requests that you use to manage the resource instance.

The following example shows a directory extension definition.

##### Request
```msgraph-interactive
GET https://graph.microsoft.com/v1.0/applications/30a5435a-1871-485c-8c7b-65f69e287e7b/extensionProperties
```

##### Response

```http
{
    "@odata.context": "https://graph.microsoft.com/v1.0/$metadata#applications('30a5435a-1871-485c-8c7b-65f69e287e7b')/extensionProperties",
    "value": [
        {
            "id": "4e3dbc8f-ca32-41b4-825a-346215d7d20f",
            "deletedDateTime": null,
            "appDisplayName": "jobStatTracker",
            "dataType": "String",
            "isSyncedFromOnPremises": false,
            "name": "extension_b7d8e648520f41d3b9c0fdeb91768a0a_jobGroup",
            "targetObjects": [
                "User"
            ]
        }
    ]
}
```

The following example shows how the custom properties and associated data are presented on a resource instance. The extension property will be returned by default through the `beta` endpoint, but only on `$select` through the `v1.0` endpoint.

##### Request
```msgraph-interactive
GET https://graph.microsoft.com/v1.0/users?$select=id,displayName,extension_b7d8e648520f41d3b9c0fdeb91768a0a_jobGroup,extension_b7d8e648520f41d3b9c0fdeb91768a0a_shareReviewsPrivately
```

##### Response
```http
{
    "@odata.context": "https://graph.microsoft.com/v1.0/$metadata#users(id,displayName,extension_b7d8e648520f41d3b9c0fdeb91768a0a_jobGroup,extension_b7d8e648520f41d3b9c0fdeb91768a0a_shareReviewsPrivately)",
    "value": [
        {
            "extension_b7d8e648520f41d3b9c0fdeb91768a0a_jobGroup": "JobGroupK",
            "extension_b7d8e648520f41d3b9c0fdeb91768a0a_shareReviewsPrivately": "Yes"
        }
    ]
}
```

### 3. Schema extensions

[Microsoft Graph schema extensions](/graph/api/resources/schemaextension) are conceptually similar to directory extensions. First, you create your schema extension definition. Then, use it to extend supported resource instances with strongly-typed custom properties. In addition, you can control the [status](/graph/api/resources/schemaextension#schema-extensions-lifecycle) of your schema extension and let it be discoverable by other apps.

For the list of resource types that support schema extensions, see [Choose an extension type for your application](#choose-an-extension-type-for-your-application).

> [!VIDEO https://www.youtube-nocookie.com/embed/3MOAlUFNus0]

#### Developer experience

When creating a schema extension definition, you must provide a unique name for its **id**. There are two naming options:

- If you already have a vanity `.com`,`.net`, `.gov`, `.edu` or a `.org` domain that you've verified with your tenant, you can use the domain name along with the schema name to define a unique name, in this format *{domainName}*_*{schemaName}*. For example, if your vanity domain is `contoso.com`, you can define an **id** of `contoso_mySchema`. This option is highly recommended.
- If you don’t have a verified vanity domain, you can set the **id** to a schema name (without a domain name prefix). For example, `mySchema`. Microsoft Graph will assign a string ID for you based on the supplied name, in this format: `ext{8-random-alphanumeric-chars}_{schema-name}`. For example, `extkvbmkofy_mySchema`.

The **id** will be the name of the complex type that will store your data on the extended resource instance.

Once a schema extension is registered, it's available to be used by all applications in the same tenant as the associated owner application (when in the `InDevelopment` state) or by all applications in any tenant (when in the `Available` state). Like directory extensions, authorized apps have the ability to read and write data on any extensions defined on the target object.

Unlike open extensions, you manage the [schema extension definitions](/graph/api/resources/schemaextension) and their data on the extended resource instance as separate sets of API operations. To manage the schema extension data on the extended resource instance, use the same REST request that you use to manage the resource instance.

The following example shows a schema extension definition.

##### Request
```msgraph-interactive
GET https://graph.microsoft.com/v1.0/schemaExtensions
```

##### Response

```http
{
    "@odata.context": "https://graph.microsoft.com/v1.0/$metadata#schemaExtensions",
    "value": [
        {
            "id": "ext6zw22v9e_graphLearnCourses",
            "description": "Graph Learn training courses extensions",
            "targetTypes": [
                "user"
            ],
            "status": "Available",
            "owner": "da2d15ee-30c0-4732-8f5d-84158b8cb8aa",
            "properties": [
                {
                    "name": "courseId",
                    "type": "Integer"
                },
                {
                    "name": "courseName",
                    "type": "String"
                },
                {
                    "name": "courseType",
                    "type": "String"
                }
            ]
        }
    ]
}
```

The following example shows how the custom properties and associated data is presented on a resource instance. You read the custom properties on a resource instance only by specifying the extension name in a `$select` request.


##### Request
```msgraph-interactive
GET https://graph.microsoft.com/v1.0/users/3fbd929d-8c56-4462-851e-0eb9a7b3a2a5?$select=id,displayName,ext6zw22v9e_graphLearnCourses
```

##### Response
```http
{
    "@odata.context": "https://graph.microsoft.com/v1.0/$metadata#users(id,displayName,ext6zw22v9e_graphLearnCourses)/$entity",
    "id": "3fbd929d-8c56-4462-851e-0eb9a7b3a2a5",
    "displayName": "MOD Administrator",
    "ext6zw22v9e_graphLearnCourses": {
        "@odata.type": "#microsoft.graph.ComplexExtensionValue",
        "courseId": 100,
        "courseName": "Explore Microsoft Graph",
        "courseType": "Online"
    }
}
```

For more information about how to use schema extensions to add custom properties and associated data, see [schemaExtension resource type](/graph/api/resources/schemextension) and [Add custom properties to groups using schema extensions](extensibility-schema-groups.md).

### 4. Open extensions

[Microsoft Graph open extensions](/graph/api/resources/opentypeextension) are [open types](https://www.odata.org/getting-started/advanced-tutorial/#openType) that offer a simple and flexible way to add untyped data directly to a resource instance. These extensions aren't strongly typed, discoverable, or filterable.

For the list of resource types that support Microsoft Graph open extensions, see [Choose an extension type for your application](#choose-an-extension-type-for-your-application).

> [!VIDEO https://www.youtube-nocookie.com/embed/ibdlADb8IZc]

#### Developer experience

Open extensions, together with their data, are accessible through the **extensions** navigation property of the resource instance.

The **extensionName** property is the only *pre-defined*, writable property in an open extension. When creating an open extension, you must assign the **extensionName** property a name that is unique within the tenant. One way to do this is to use a reverse domain name system (DNS) format that is dependent on *your own domain*, for example, `Com.Contoso.ContactInfo`. **Do not use the Microsoft domain (`Com.Microsoft` or `Com.OnMicrosoft`) in an extension name**.

The following example shows an open type definition and how the custom properties and associated data is presented on a resource instance.


##### Request
```msgraph-interactive
GET https://graph.microsoft.com/v1.0/users/3fbd929d-8c56-4462-851e-0eb9a7b3a2a5/extensions
```

##### Response
```http
{
    "@odata.context": "https://graph.microsoft.com/beta/$metadata#users('3fbd929d-8c56-4462-851e-0eb9a7b3a2a5')/extensions",
    "value": [
        {
            "@odata.type": "#microsoft.graph.openTypeExtension",
            "extensionName": "com.contoso.roamingSettings",
            "theme": "dark",
            "color": "purple",
            "lang": "Japanese",
            "id": "com.contoso.roamingSettings"
        }
    ]
}
```

For more information about how to use open extensions to add custom properties and associated data, see [openTypeExtension resource type](/graph/api/resources/opentypeextension) and [Add custom properties to users using open extensions](extensibility-open-users.md).

## Choose an extension type for your application

The table below contrasts and compares the extension types, which should help you decide which option is most appropriate for your scenario.

| Capability | Extension attributes 1-15 | Directory extensions | Schema extensions | Open extensions |
|--|--|--|--|--|
| Supported resource types | [user][] <br/>[device][] | [user][] <br/> [group][] [application][] <br/>[device][] <br/> [organization][] | [user][] <br/> [group][] <!--<br/> [administrativeUnit][]--> <br/> [contact][] <br/> [device][] <br/> [event][] (both user and group calendars) <br/> [message][] <br/> [organization][] <br/> [post][] <br/> [todoTask][] <br/> [todoTaskList][] | [user][] <br/> [group][] <!--<br/> [administrativeUnit][]--> <br/> [contact][] <br/> [device][] <br/> [event][]<sup>1</sup> (both user and group calendars) <br/> [message][] <br/> [organization][] <br/> [post][] |
| Strongly-typed | No | Yes | Yes | No |
| Filterable | Yes | Yes | Yes | No |
| Managed via | Microsoft Graph <br/> Exchange admin center | Microsoft Graph | Microsoft Graph | Microsoft Graph |
| Sync data from on-premises to extensions using [AD connect][] | Yes, for users | [Yes][ADConnect-YES] | No | No |
| Create [dynamic membership rules][] using custom extension properties and data | [Yes][DynamicMembership-YES] | [Yes][DynamicMembership-YES] | No | No |
| Usable for customizing token claims | Yes | [Yes][DirectoryExt-CustomClaims] | No | No |
| Available in Azure AD B2C | Yes | [Yes][B2CDirectoryExt] | Yes | Yes |
| Limits | <li>15 predefined attributes per user or device resource instance | <li>100 extension values per resource instance | <li>Maximum of five definitions per owner app <br/><li> 100 extension values per resource instance (directory objects only) | <li>Two open extensions per creator app per resource instance<sup>2</sup> <br/><li> Max. of 2Kb per open extension<sup>2</sup><li> For Outlook resources, each open extension is stored in a [MAPI named property][MAPI-named-property]<sup>3</sup> |


> [!NOTE]
> 
> <sup>1</sup> Due to an existing service limitation, delegates cannot create open extension-appended events in shared mailbox calendars. Attempts to do so will result in an `ErrorAccessDenied` response.
>
> <sup>2</sup> These limits on open extensions apply to the following directory resources: **user**, **group**, **device**, <!--**administrativeUnit**,--> and **organization**.
>
> <sup>3</sup> Each [open extension](/graph/api/resources/opentypeextension) is stored in a [MAPI named property](/office/client-developer/outlook/mapi/mapi-named-properties), which are a limited resource in a user's mailbox. This limit applies to the following Outlook resources: **message**, **event**, and **contact**
>
> You can manage all extensions when you're signed in with a work or school account. Additionally, you can manage open extensions for the following resources when signed-in with a personal Microsoft account: **event**, **post**, **group**, **message**, **contact**, and **user**.

## Permissions

The same [permissions](./permissions-reference.md) that are required to read from or write to a specific resource are also required to read from or write to any extensions data on that resource. For example, for an app to update any user's profile with custom app data, the app must have been granted the *User.ReadWrite.All* permission.

## Known limitations

For known limitations using extensions, see the [extensions section](known-issues.md#extensions) in the known issues article.

## See also

- [Add custom properties to users using open extensions](extensibility-open-users.md)
- [Add custom properties to groups using schema extensions](extensibility-schema-groups.md)
- [Microsoft 365 domains](/office365/servicedescriptions/office-365-platform-service-description/domains)
- [Adding and verifying a domain for a Microsoft 365 tenant](https://office365support.ca/adding-and-verifying-a-domain-for-the-new-office-365/)


<!-- Links -->

[user]: /graph/api/resources/user
[group]: /graph/api/resources/group
[contact]: /graph/api/resources/contact
[administrativeUnit]: /graph/api/resources/administrativeunit
[application]: /graph/api/resources/application
[device]: /graph/api/resources/device
[event]: /graph/api/resources/event
[message]: /graph/api/resources/message
[organization]: /graph/api/resources/organization
[post]: /graph/api/resources/post
[todoTask]: /graph/api/resources/todotask
[todoTaskList]: /graph/api/resources/todotasklist
[servicePrincipal]: /graph/api/resources/serviceprincipal
[AD connect]: /azure/active-directory/hybrid/whatis-hybrid-identity?context=/azure/active-directory/enterprise-users/context/ugr-context
[ADConnect-YES]: /azure/active-directory/hybrid/how-to-connect-sync-feature-directory-extensions
[dynamic membership rules]: /azure/active-directory/enterprise-users/groups-dynamic-membership
[DynamicMembership-YES]: /azure/active-directory/enterprise-users/groups-dynamic-membership#extension-properties-and-custom-extension-properties
[DirectoryExt-CustomClaims]: /azure/active-directory/develop/active-directory-optional-claims#configuring-directory-extension-optional-claims
[B2CDirectoryExt]: /azure/active-directory-b2c/user-profile-attributes#extension-attributes
[MAPI-named-property]: /office/client-developer/outlook/mapi/mapi-named-properties