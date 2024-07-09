---
id: user-repo
title: Repository Metadata
---

## GET /\{user\}/\{repo\}

Retrieves information about a user's repository.

### URL

`GET https://api.synodic.ai/{user}/{repo}`

### Path Parameters

- **\{user\}**: username (string)
- **\{repo\}**: repository name (string)

### Example Request

```bash
curl -X GET "https://api.synodic.ai/{username}/{repo}"
```