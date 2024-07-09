---
id: remove-class
title: Remove Dataset Class
---

## GET /\{user\}/\{repo\}/dataset/classes/remove

Removes a class from the specified repository's dataset.

### URL

`GET https://api.synodic.ai/{user}/{repo}/dataset/classes/remove`

### Path Parameters

- **\{user\}**: username (string)
- **\{repo\}**: repository name (string)

### Headers

- **remove_class_index**: the index of the class being removed

### Example Request

```bash
curl -X GET "https://api.synodic.ai/{username}/{repo}/dataset/classes/remove" \
-H "remove_class_index: 1"