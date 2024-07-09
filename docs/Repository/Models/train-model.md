---
id: train-model
title: Train Model
---

## GET /\{user\}/\{repo\}/models/train

Initiates the training of the specified model for the user's repository.

### URL

`GET https://api.synodic.ai/{user}/{repo}/models/train`

### Path Parameters

- **\{user\}**: username (string)
- **\{repo\}**: repository name (string)

### Headers

- **model**: the model to be trained, include the variant (e.g., yolov8n, yolov9c, etc.)
- **train_percent**: int between 0 and 100 (train_percent, test_percent, valid_percent sum to 100)
- **test_percent**: int between 0 and 100 (train_percent, test_percent, valid_percent sum to 100)
- **valid_percent**: int between 0 and 100 (train_percent, test_percent, valid_percent sum to 100)
- **epochs**: the number of training epochs

### Example Request

```bash
curl -X GET "https://api.synodic.ai/{user}/{repo}/models/train" \
-H "model: yolov8n" \
-H "train_percent: 70" \
-H "test_percent: 20" \
-H "valid_percent: 10" \
-H "epochs: 50"