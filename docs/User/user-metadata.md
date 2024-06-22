---
id: api-user-get
title: Get User Metadata
sidebar_label: User Metadata
---

## Initialize User

### Endpoint
`GET https://fqk4k22rqc.execute-api.us-east-1.amazonaws.com/{user}/init`

### Path Parameters
- **\{user\}**: Either the username or Firebase UID.

### Example Request
```bash
curl -X GET "https://fqk4k22rqc.execute-api.us-east-1.amazonaws.com/{user}/init"
```