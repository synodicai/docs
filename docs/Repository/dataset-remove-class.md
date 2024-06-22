---
id: remove-class
title: Remove Dataset Class
---

## GET /\{user\}/\{repo\}/dataset/classes/remove

Removes a class from the specified repository's dataset.

### URL

`GET https://fqk4k22rqc.execute-api.us-east-1.amazonaws.com/{user}/{repo}/dataset/classes/remove`

### Path Parameters

- **\{user\}**: username (string)
- **\{repo\}**: repository name (string)

### Headers

- **remove_class_index**: the index of the class being removed

### Example Request

```bash
curl -X GET "https://fqk4k22rqc.execute-api.us-east-1.amazonaws.com/{username}/{repo}/dataset/classes/remove" \
-H "remove_class_index: 1"