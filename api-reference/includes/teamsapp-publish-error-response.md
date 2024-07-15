### Error response

If you send a request to upload an app manifest that contains missing information or errors, you receive an error message that includes the inner error code `UnableToParseTeamsAppManifest`. The *details* property of the inner error contains the error code and the error message. The following table describes the most frequently encountered error codes:

| Error code | Error message | Description |
| :---- | ---- | ---- |
|`Serialization_FileNotValidJson`| The file couldn't be parsed as a JSON object.| The submitted file didn't comply with a valid JSON format. |
|`Serialization_ManifestVersionPropertyMissing`| The file doesn't contain the "{0}" property.| The `manifestVersion` property is missing in the app manifest file. Here, {0} is the string for `manifestVersion` property.|
|`Serialization_FileMissing`| The file {0} couldn't be found in the app package.| The expected file is missing in the app package.|
|`Serialization_TrailingCommaInManifestJsonFile`| Manifest json file contains trailing comma.| The app manifest file contains trailing comma.|
|`SchemaError_MultipleOf`| Integer {0} isn't a multiple of {1}.| The app manifest file failed the `multipleOf` validation of the schema. Here, {0} represents the integer value and {1} indicates the required multiple. |
|`SchemaError_Maximum`| Integer {0} exceeds maximum value of {1}.| The app manifest file failed the `maximum` validation of the schema. Here, {0} represents the value that exceeds the maximum limit and {1} represents the maximum limit. |
|`SchemaError_Minimum`| Integer {0} is less than minimum value of {1}.|The app manifest file failed the `minimum` validation of the schema. Here, {0} represents the value that exceeds the minimum limit and {1} represents the minimum limit.|
|`SchemaError_MaximumLength`| String {0} exceeds maximum length of {1}.| The app manifest file failed the `maximumLength` validation of the schema. Here, {0} represents the string that exceeds the maximum length and {1} represents the maximum length.|
|`SchemaError_MinimumLength`| String {0} is less than minimum length of {1}. | The app manifest file failed the `minimumLength` validation of the schema. Here, {0} represents the string that is less than the minimum length and {1} represents the minimum.|
|`SchemaError_Pattern`| String {0} doesn't match regex pattern "{1}". | The app manifest file failed the `pattern` validation of the schema. Here, {0} represents the value that doesn't match the pattern and {1} represents the expected pattern.|
|`SchemaError_ContentEncoding`| String {0} doesn't validate against content encoding {1}.| The app manifest file failed the `contentEncoding` validation of the schema. Here, {0} represents the string that doesn't match content encoding and {1} represents the expected content encoding.|
|`SchemaError_Format`| String {0} doesn't validate against format {1}.| The app manifest file failed the `format` validation of the schema. Here, {0} represents the string that isn't in the expected format and {1} represents the expected format.|
|`SchemaError_Type`| Value {0} isn't of the expected type {1}.| The app manifest file failed the `type` validation of the schema. Here, {0} represents the string that isn't in the expected type and {1} represents the expected type.|
|`SchemaError_AdditionalItems`| The schema doesn't allow additional items.| The app manifest file failed the `additionalItems` validation of the schema.|
|`SchemaError_MaximumItems`| Array item count {0} exceeds maximum count of {1}.| The app manifest file failed the `maximumItems` validation of the schema. Here, {0} represents the number of elements in the array and {1} represents the maximum allowed.|
|`SchemaError_MinimumItems`| Array item count {0} is less than minimum count of {1}.| The app manifest file failed the `minimumItems` validation of the schema. Here, {0} represents the number of elements in the array and {1} represents the minimum allowed.|
|`SchemaError_UniqueItems`| Array contains items that aren't unique.| The app manifest file failed the `uniqueItems` validation of the schema.|
|`SchemaError_MaximumProperties`| Object property count {0} exceeds maximum count of {1}.| The app manifest file failed the `maximumProperties` validation of the schema. Here, {0} represents the number of properties provided and {1} represents the maximum allowed properties.|
|`SchemaError_MinimumProperties`| Object property count {0} is less than minimum count of {1}.|The app manifest file failed the `minimumProperties` validation of the schema. Here, {0} represents the number of properties provided and {1} represents the minimum allowed properties.|
|`SchemaError_Required`| Required properties are missing from object: {0}.| The app manifest file failed the `required` validation of the schema. Here, {0} represents the required properties. |
|`SchemaError_AdditionalProperties`| Property {0} hasn't been defined and the schema doesn't allow additional properties.| The app manifest file failed the `additionalProperties` validation of the schema. Here, {0} represents the additional property.|
|`SchemaError_Dependencies`|Dependencies for property {0} failed. Missing required keys.| The app manifest file failed the `dependencies` validation of the schema. Here, {0} represents the property that failed.|
|`SchemaError_Enum`| Value {0} isn't defined in the enum.| The app manifest file failed the `enum` validation of the schema. Here, {0} represents the value that isn't in the enum.|
|`SchemaError_AllOf`| JSON doesn't match all schemas from "allOf".| The app manifest file failed the `allOf` validation of the schema. The `allOf` isn't localizable.|
|`SchemaError_AnyOf`| JSON doesn't match any schemas from "anyOf".| The app manifest file failed the `anyOf` validation of the schema. The `anyOf` isn't localizable.|
|`SchemaError_OneOf`| JSON is valid against more than one schema from "oneOf".| The app manifest file failed the `oneOf` validation of the schema. The `oneOf` isn't localizable.|
|`SchemaError_Not`| JSON is valid against schema from "not".| The app manifest file failed the `not` validation of the schema. The `not` isn't localizable.|
|`SchemaError_Id`| Duplicate schema ID {0} encountered.| The app manifest file failed the `id` validation of the schema. Here, {0} represents the `id` of the schema.|
|`SchemaError_PatternProperties`| Couldn't test property names with regex pattern "{0}".| The app manifest file failed the `patternProperties` validation of the schema. Here, {0} represents the pattern for the properties.|
|`SchemaError_Valid`| Schema always fails validation.| The app manifest file failed the `valid` validation of the schema.|
|`SchemaError_Const`| Value {0} doesn't match constant {1}.| The app manifest file failed the `const` validation of the schema. Here, {0} represents the value that failed and {1} represents the correct value.|
|`SchemaError_Contains`| Array doesn't contain a required item.| The app manifest file failed the `contains` validation of the schema.|
|`SchemaError_Then`|JSON doesn't match schema from "then".| The app manifest file failed the `then` validation of the schema. The `then` isn't localizable.|
|`SchemaError_Else`| JSON doesn't match schema from "else".|The app manifest file failed the `else` validation of the schema. The `else` isn't localizable.|
| `SchemaError_Other`| The value doesn't conform to the schema for this property.| The app manifest file failed other unhandled validations of the schema.|
|`ActivityGroupIdFromActivitiesTypeValidation` 	| ActivityGroupId field in ActivityType must be a subset of ID field in ActivityGroup.| The `ActivityGroupId` field in `ActivityType` isn't a subset of the `Id` field in `ActivityGroup` in the app manifest.|
|`ActivityTypesMustExistWithActivitiesGroupValidation` |	Manifest shouldn't contain Activity Group when Activity Types is missing.| The `ActivityGroup` property is available, but `ActivityType` property is missing in the app manifest.|
|`ApiSecretServiceAuthTypeComposeExtensionContainsMsftEntraConfiguration`|API-based compose extension with apiSecretServiceAuth authType have microsoftEntraConfiguration defined.| The API-based compose extension has `microsoftEntraConfiguration` defined in the app manifest.|
|`ApiSecretServiceAuthTypeComposeExtensionContainsNoApiSecretRegistrationId`| API-based compose extension with apiSecretServiceAuth authType have no apiSecretRegistrationId defined.| The API-based compose extension with `apiSecretServiceAuth` authType without `apiSecretRegistrationId` defined in the app manifest.|
|`ApiSecretServiceAuthTypeComposeExtensionContainsNoApiSecretServiceAuthConfiguration` | API-based compose extension with apiSecretServiceAuth authType have no apiSecretServiceConfiguration.| The API-based compose extension doesn't set `supportsSingleSignOn` to `true` in the app manifest.|
|`ApiBasedComposeExtensionManifestCommandIdsNotIncludedInOperationIdsOnApiSpecficationFile`| Command Ids on manifest aren't included in Operation Ids on API specification file.| The error that occurs when the `Command Ids` in the app manifest aren't included in `Operation Ids` on API specification file.|
|`ApiBasedComposeExtensionWithBotId`| API-based compose extension can't have botId defined.| The API-based compose extension has `botId` defined in the app manifest.|
|`ApiBasedComposeExtensionWithCanUpdateConfiguration`|API-based compose extension can't have canUpdateConfiguration defined on manifest.| The API-based compose extension has `canUpdateConfiguration` defined in the app manifest.|
|`ApiBasedComposeExtensionWithNoParameter`| API-based compose extension must have command parameters defined on manifest.| The API-based compose extension doesn't have any command parameters defined in the app manifest.|
|`ApiBasedComposeExtensionApiResponseRenderingTemplateFileNullOrEmpty`| API-based compose extension must have apiResponseRenderingTemplateFile defined on manifest.| The API-based compose extension doesn't have the `apiResponseRenderingTemplateFile` defined in the app manifest.|
|`ApiBasedComposeExtensionApiSpecificationFileNullOrEmpty`| API-based compose extension must have apiSpecificationFile defined on manifest. | The API-based compose extension doesn't have the `apiSpecificationFile` defined in the app manifest.|
|`MsftEntraAuthTypeComposeExtensionContainsApiSecretServiceConfiguration`|API-based compose extension with microsoftEntra authType have apiSecretServiceConfiguration defined. |The API-based compose extension has `apiSecretServiceConfiguration` defined in the manifest.|
|`MsftEntraAuthTypeComposeExtensionContainsNoMsftEntraConfiguration`|API-based compose extension with microsoftEntra authType have no microsoftEntraConfiguration defined.| The API-based compose extension doesn't have `microsoftEntraConfiguration` defined in the app manifest.|
|`MsftEntraAuthTypeComposeExtensionWebApplicationInfoOrResourceNotDefined`|API-based compose extension with microsoftEntra authType have no webApplicationInfo or resource defined on manifest.| The API-based compose extension with `microsoftEntra` authType doesn't have `webApplicationInfo` or `resource` defined in the app manifest.|
|`MsftEntraAuthTypeComposeExtensionSupportsSingleSignOnFalse` | API-based compose extension with microsoftEntra authType doesn't set supportsSingleSignOn to true.| The API-based compose extension doesn't set `supportsSingleSignOn` to `true` in the app manifest.|
|`MsftEntraAuthTypeComposeExtensionResourceURLNotMatchServerURLOnApiSpec` |API-based compose extension with microsoftEntra authType resource URL on manifest doesn't match server URL on API specification file.| The API-based compose extension with `microsoftEntra` authType resource URL in the app manifest doesn't match server URL in the API specification file.|
|`NoAuthTypeComposeExtensionContainsAuthConfiguration` |API-based compose extension with none authType have auth-related configuration defined.| The API-based compose extension with authType `microsoftEntraConfiguration` or `apiSecretServiceConfiguration` isn't defined in the app manifest.|
|`ApiSpecificationFileContainUnsupportedHttpMethod`| API-based compose extension have server urls that have unsupported http method defined on apiSpecificationFile. Currently only GET and POST are supported.| The API-based compose extension has unsupported `http` method defined in the `apiSpecificationFile`.|
|`ApiSpecificationFileRequiredParameterContainUnsupportedLocation`| API-based compose extension have unsupported parameter location defined on apiSpecificationFile for {0}. Currently only path and query supported.| The API-based compose extension has unsupported parameter location defined in the `apiSpecificationFile`.|
|`ApiSpecificationFileRequestBodyContainUnsupportedMediaType`|API-based compose extension have unsupported media type defined in request body on apiSpecificationFile. Currently only application/json is supported.| The API-based compose extension have unsupported `media` type defined in request body in the `apiSpecificationFile`.|
|`ApiSpecificationFileRequestBodyContainUnsupportedSchemaType`| API-based compose extension have unsupported schema type defined in request body on apiSpecificationFile. Currently arrays aren't supported.| The API-based compose extension have unsupported schema type defined in request body in the `apiSpecificationFile`.|
|`ApiSpecificationFileRequestBodySchemaContainKeywords` | API-based compose extension have keywords.|The API-based compose extension have keywords defined in request body in the `apiSpecificationFile`.|
|`ApiSpecificationFileRequiredParameterOrPropertyNotDefinedOnManifest`| API-based compose extension have required parameters or properties {0} not defined on manifest.| The API-based compose extension have `required` parameter isn't defined in the app manifest.|
|`ApiSpecificationFileResponseContainUnsupportedMediaType`| API-based compose extension have unsupported media type defined in response on apiSpecificationFile. Currently only application/json supported.	| The API-based compose extension have unsupported `media` type defined in response in the `apiSpecificationFile`.|
|`ApiSpecificationFileServerUrlsContainHttp`| API-based compose extension have server urls that have http protocol defined on apiSpecificationFile.| The API-based compose extension have server urls that contain `http` protocol in the `apiSpecificationFile`.|
|`ApiSpecificationFileServerUrlsContainInvalidUrl`| API-based compose extension have server urls that are invalid URL defined on apiSpecificationFile.| The API-based compose extension have `invalid` URL defined in the `apiSpecificationFile`.|
|`ServerUrlsMissingOnApiSpecificationFile`| API-based compose extension have no server urls defined on apiSpecificationFile.| The error that occurs The API-based compose extension have no server urls defined in the `apiSpecificationFile`.|
|`BotBasedComposeExtensionApiResponseRenderingTemplateFileExists` |Bot based compose extension can't have apiResponseRenderingTemplateFile defined.|The bot-based compose extension have `apiResponseRenderingTemplateFile` property defined in the app manifest.|
|`BotBasedComposeExtensionApiSpecificationFileExists` |Bot based compose extension can't have apiSpecificationFile defined.|The bot-based compose extension have API specification file defined in the app manifest.|
|`BotBasedComposeExtensionBotIdNotGuid` |Bot based compose extension must have GUID botId.| The bot-based compose extension `botId` isn't GUID.|
|`CommonAppIdIsNotGuid`| Field 'ID' isn't a Guid in the manifest.| The `appId` isn't GUID.|
|`CommonAppIdIsRequiredField`| Required field 'ID' is missing in the manifest.| The `appId` isn't provided.|
|`CommonManifestVersionIsRequiredField`|The required field in manifest 'manifest Version' is missing.| The manifest version isn't provided.|
|`CommonSchemaUrlIsRequiredField`| Schema URL must be present.| The schema isn't provided.|
|`DashboardCardBothIconNameAndUrlPresent`| Dashboard cards icon shouldn't contain both icon name and URL.| Dashboard cards icon mustn't contain both icon name and URL.|
|`DashboardCardEntityIdsAreNotUnique`| Dashboard card entity IDs should be unique.| Entity Ids for dashboards card aren't unique.|
|`DeveloperNameIsRequiredField`| Required field 'developer name' is missing in the manifest.| The developer name isn't provided.|
|`DeveloperNameLengthCheck`| Maximum character length must not exceed 32 chars.| The developer name is more than 32 characters long.|
|`DeveloperPrivacyUrlIsRequiredField`| Required field 'privacyUrl' is missing in the manifest.| The `privacyUrl` is missing in the app manifest. |
|`DeveloperPrivacyUrlMustBeHttps`| Privacy URL must be secured Support URL (HTTPS).| The developer privacy URL did not use HTTPS.|
|`DeveloperTermsOfUseUrlIsRequiredField`| Required field 'termsOfUseUrl' is missing in the manifest.| The termsOfUseUrl** is missing.|
|`DeveloperTermsOfUseUrlMustBeHttps`|Terms Of Use URL must be secured Support URL (HTTPS).| The developer terms of use URL isn't `https`.|
|`DeveloperWebsiteUrlIsRequiredField`| Required field 'websiteUrl' is missing in the manifest.| The developer website URL is missing.|
|`DeveloperWebsiteUrlMustBeHttps`| Website URL must be secured Support URL (HTTPS).| The developer website URL didn't use HTTPS.|
|`UniqueActivityTypeInActivitiesValidation` |Manifest shouldn't contain duplicate Activity Type.| The activity type isn't unique in the app manifest.|
|`UniqueIdInActivitiesGroupValidation` |Manifest shouldn't contain duplicate ID in Activity Groups.| The activity group ID isn't unique in the app manifest.|
|`FullDescriptionCannotBeEmpty` |Full Description can't be empty.| The full description is empty.|
|`FullDescriptionLengthCheck`| Maximum character length for long description must not exceed 4,000 chars.| The full description length is more than 4,000 characters.|
|`GroupChatForBotsLessThanV13`| Please upgrade the version of manifest to V1.3 as group chat bot is supported in manifest v1.3 onwards.| The `groupChat` scope for bots isn't supported in the app manifest version 1.3 and below.|
|`GroupChatForConfigurableTabsLessThanV13`| Please upgrade the version of manifest to V1.3 as group chat configurable tabs is supported in manifest v1.3 onwards.|The `groupChat` scope for configurable tabs isn't supported in the app manifest version 1.3 and below.|
|`InvalidColor32x32IconHeightAndWidth`|Color 32x32 icon should be 32x32 with only white and transparent.| The color 32x32 icon doesn't have the correct dimensions.|
|`InvalidColorIconHeightAndWidth`| Color Icon isn't as per the required dimension.| The dimensions of the color icon are incorrect.|
|`InvalidOutlineIconHeightAndWidth` | Small icon should be 32x32 with only white and transparent.| The dimensions of the outline icon are incorrect.|
|`InvalidOutlineIconTransparency`| Outline icon isn't transparent. It's Alpha.| The outline icon isn't transparent. It contains pixels that aren't transparent or white, with an Alpha, R, G, B value of {0}, {1}, {2}, {3}.	|
|`ParameterOnManifestNotDefinedOnApiSpecFile` | API-based compose extension have parameters {0} on manifest not defined on API specification file.| The API-based compose extension parameters in the app manifest aren't defined on API specification file. |
|`ReservedActivitiesValidation`| Manifest shouldn't contain reserved Activity Type 'systemDefault'.| The `systemDefault` activity type is defined in the app manifest.|
|`ReservedStaticTabNameShouldBeNull`| Reserved tab "Name" property shouldn't be specified.| The reserved `staticTabs` name property was specified.|
|`ShortDescriptionCannotBeEmpty`| Short Description can’t be empty| The short description was empty.|
|`ShortDescriptionLengthCheck`|Maximum character length for short description must not exceed 80 chars.| The short description is more than 80 characters long.|
|`ShortNameEqualsReservedName`|Short name of the app can't be reserved name.| The short name is reserved name.|
|`ShortNameIsRequiredField`| Short name of the app can't be empty.| The short name is empty.|
|`StaticTabNameCouldNotBeEmpty`| Non-reserved staticTabs "Name" property can't be empty.| The `staticTabs` name property is empty.|
|`BotIdIsNotGuid`| BotId isn't a Guid value.| The `BotId` isn't GUID in the app manifest.|
|`VersionCannotBeEmpty`| Required field "version" is missing in the manifest.| The version in the app package is `null`.|
|`VersionContainsOnlyNumbersDotSeparated`| App version supports only numbers in the '#.#.#' format.| The version in the app package doesn't match pattern `#.#.#`.|
|`VersionHasMajorLessThan1`|App version shouldn't start with '0'. Ex: 0.0.1 or 0.1 aren't valid app versions and 1.0 / 1.5.1 / 1.0.0 / 2.5.0 are valid app versions. In case of new update in manifest to an existing app in store. | The app version is less than 1.0. You need to upgrade your app version. For example, if the current version of your app in the store is 1.0 and you’re submitting an update for validation, the app version must be higher than 1.0.|
|`ShortNameLengthCheck` |Maximum character length for Short Name must not exceed 30 chars.|The short name exceeds 30 characters.|
|`ApiSpecificationFileParameterContainUnsupportedSchemaType` |API-based compose extension have unsupported parameter schema type defined on apiSpecificationFile.Arrays aren't supported.|The API-based compose extension has an unsupported parameter schema type defined in the `apiSpecificationFile`.|