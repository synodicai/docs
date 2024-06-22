---
id: user-repo
title: Repository Metadata
---

## GET /\{user\}/\{repo\}

Retrieves information about a user's repository.

### URL

`GET https://fqk4k22rqc.execute-api.us-east-1.amazonaws.com/{user}/{repo}`

### Path Parameters

- **\{user\}**: username (string)
- **\{repo\}**: repository name (string)

### Example Request

```bash
curl -X GET "https://fqk4k22rqc.execute-api.us-east-1.amazonaws.com/{username}/{repo}"
```