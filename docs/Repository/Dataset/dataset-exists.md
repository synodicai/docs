---
id: check-repo-exists
title: Check if Repository Exists
---

## GET /\{user\}/\{repo\}/exists

Checks if the specified repository exists for the user.

### URL

`GET https://api.synodic.ai/{user}/{repo}/exists`

### Path Parameters

- **\{user\}**: username (string)
- **\{repo\}**: repository name (string)

### Example Request

```bash
curl -X GET "https://api.synodic.ai/{user}/{repo}/exists"