---
description: "Automatically generated file. DO NOT MODIFY"
---

```python



graph_client = GraphServiceClient(credentials, scopes)

request_body = DeletePasswordSingleSignOnCredentialsPostRequestBody(
	id = "314ac440-129f-4cb3-ad61-24ef4a7de1d9",
)

await graph_client.users.by_user_id('user-id').delete_password_single_sign_on_credentials.post(request_body)


```