---
id: download-model
title: Download Model
---

## GET /\{user\}/\{repo\}/models/download

Downloads the specified model's weights for the given epoch.

### URL

`GET https://api.synodic.ai/{user}/{repo}/models/download`

### Path Parameters

- **\{user\}**: username (string)
- **\{repo\}**: repository name (string)

### Headers

- **model**: the model_id of the trained model
- **epoch**: the epoch that the weights should be downloaded from. It is probably best to set this to the last epoch (which would be the total_epochs - 1)

### Example Request

```bash
curl -X GET "https://api.synodic.ai/{user}/{repo}/models/download" \
-H "model: model_id" \
-H "epoch: 49"