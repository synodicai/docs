---
id: delete-user
title: Delete User
---

## DELETE /\{user\}/delete

Deletes the user data.

### URL

`ANY https://fqk4k22rqc.execute-api.us-east-1.amazonaws.com/{user}/delete`

### Path Parameters

- **\{user\}**: username (string)

### Headers

- **firebase_uid**: (string)

### Example Request

```bash
curl -X POST "https://fqk4k22rqc.execute-api.us-east-1.amazonaws.com/{user}/delete"
```