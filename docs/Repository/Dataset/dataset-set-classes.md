---
id: set-dataset-classes
title: Set Dataset Classes
---

## GET /\{user\}/\{repo\}/dataset/classes

Sets the classes for the specified repository's dataset.

### URL

`GET https://api.synodic.ai/{user}/{repo}/dataset/classes`

### Path Parameters

- **\{user\}**: username (string)
- **\{repo\}**: repository name (string)

### Headers

- **classes**: dictionary of index and class names  
  Example: `{"0": "pizza", "1": "pasta"}`

### Example Request

```bash
curl -X GET "https://api.synodic.ai/{username}/{repo}/dataset/classes" \
-H "classes: {\"0\": \"pizza\", \"1\": \"pasta\"}"