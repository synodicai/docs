---
id: view-dataset
title: View Dataset
---

## GET /\{user}/\{repo}/dataset/view

Retrieves a view of the dataset for the specified repository.

### URL

`GET https://api.synodic.ai/{user}/{repo}/dataset/view`

### Path Parameters

- **\{user}**: username (string)
- **\{repo}**: repository name (string)

### Headers

- **start**: start index of the list of files returned
- **end**: end index of the list of files returned

  OR

- **file**: specific filename

### Example Request

```bash
curl -X GET "https://api.synodic.ai/{user}/{repo}/dataset/view" \
-H "start: 0" \
-H "end: 10"

# OR

curl -X GET "https://api.synodic.ai/{user}/{repo}/dataset/view" \
-H "file: specific_filename.txt"