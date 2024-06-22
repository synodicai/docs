---
id: delete-images
title: Delete Images from Dataset
---

## POST /\{user\}/\{repo\}/dataset/image/delete

Deletes images from the specified repository's dataset.

### URL

`POST https://fqk4k22rqc.execute-api.us-east-1.amazonaws.com/{user}/{repo}/dataset/image/delete`

### Path Parameters

- **\{user\}**: username (string)
- **\{repo\}**: repository name (string)

### Body

- **images**: a list of image filenames split by "|" (vertical bar)

### Example Request

```bash
curl -X POST "https://fqk4k22rqc.execute-api.us-east-1.amazonaws.com/{user}/{repo}/dataset/image/delete" \
-H "Content-Type: application/json" \
-d '{
  "images": "image1.jpg|image2.jpg|image3.jpg"
}'