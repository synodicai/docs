---
id: autolabel-dataset
title: Autolabel Dataset
---

## POST /\{user\}/\{repo\}/dataset/autolabel

Automatically labels the dataset for the specified repository.

### URL

`POST https://fqk4k22rqc.execute-api.us-east-1.amazonaws.com/{user}/{repo}/dataset/autolabel`

### Path Parameters

- **\{user\}**: username (string)
- **\{repo\}**: repository name (string)

### Body

- **images**: a list of image filenames split by "|" (vertical bar)
- **classes**: (name is unintuitive) a list of descriptions of each class split by "|" (vertical bar), the order should correspond with the order of the classes

### Example Request

```bash
curl -X POST "https://fqk4k22rqc.execute-api.us-east-1.amazonaws.com/{username}/{repo}/dataset/autolabel" \
-H "Content-Type: application/json" \
-d '{
  "images": "image1.jpg|image2.jpg|image3.jpg",
  "classes": "class1 description|class2 description|class3 description"
}'