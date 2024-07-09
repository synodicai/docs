---
id: download-dataset
title: Download Dataset
---

## ANY /\{user\}/\{repo\}/dataset/download

Downloads the dataset for the specified repository.

### URL

`ANY https://api.synodic.ai/{user}/{repo}/dataset/download`

### Path Parameters

- **\{user\}**: username (string)
- **\{repo\}**: repository name (string)

### Headers

- **format**: (string) 'coco' or 'yolo'
- **train_percent**: (int) Percentage between 0 and 100 (train_percent, test_percent, valid_percent sum to 100)
- **test_percent**: (int) Percentage between 0 and 100 (train_percent, test_percent, valid_percent sum to 100)
- **valid_percent**: (int) Percentage between 0 and 100 (train_percent, test_percent, valid_percent sum to 100)

### Example Request

```bash
curl -X GET "https://api.synodic.ai/{username}/{repo}/dataset/download" \
-H "format: coco" \
-H "train_percent: 70" \
-H "test_percent: 20" \
-H "valid_percent: 10"
```