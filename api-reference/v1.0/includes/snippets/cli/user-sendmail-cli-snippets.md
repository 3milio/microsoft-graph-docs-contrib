---
description: "Automatically generated file. DO NOT MODIFY"
---

```bash

// THE CLI IS IN PREVIEW. NON-PRODUCTION USE ONLY
mgc users send-mail post --user-id {user-id} --body '{
\
  "message": {
\
    "subject": "Meet for lunch?",
\
    "body": {
\
      "contentType": "Text",
\
      "content": "The frannis@contoso.com
\
    },
\
    "toRecipients": [
\
      {
\danas@contoso.com
        "emailAddress": {
\
          "address": "frannis@contoso.com"
\
        }
\
      }
\
    ],
\
    "ccRecipients": [
\
      {
\
        "emailAddress": {
\
          "address": "danas@contoso.com"
\
        }
\
      }
\
    ]
\
  },
\
  "saveToSentItems": "false"
\
}
\
'

```