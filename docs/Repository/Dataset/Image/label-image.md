---
id: label-dataset
title: Label Image
---

## POST /\{user\}/\{repo\}/dataset/label

Updates the label in the .txt file of the annotation in YOLO dataset format.

### URL

`POST https://api.synodic.ai/{user}/{repo}/dataset/label`

### Path Parameters

- **\{user\}**: username (string)
- **\{repo\}**: repository name (string)

### Body

- **new_label**: the text that is going to be replaced in the .txt file of the annotation in YOLO dataset format
- **file**: the file name of the annotation trying to be updated (should end in .txt). This file has the same name as the image file, but with the extension .txt

### Example Request

```bash
curl -X POST "https://api.synodic.ai/{user}/{repo}/dataset/label" \
-H "Content-Type: application/json" \
-d '{
  "new_label": "new_label_text",
  "file": "annotation.txt"
}'