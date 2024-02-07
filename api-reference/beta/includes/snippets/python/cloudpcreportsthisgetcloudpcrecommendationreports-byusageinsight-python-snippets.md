---
description: "Automatically generated file. DO NOT MODIFY"
---

```python



graph_client = GraphServiceClient(credentials, scopes)

request_body = GetCloudPcRecommendationReportsPostRequestBody(
	report_name = CloudPcReportName.CloudPcUsageCategoryReports,
	select = [
		"UsageInsight",
	],
	group_by = [
		"UsageInsight",
	],
	filter = "",
)

await graph_client.device_management.virtual_endpoint.reports.get_cloud_pc_recommendation_reports.post(request_body)


```