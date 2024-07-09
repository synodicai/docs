---
id: api-user-get
title: User Metadata
sidebar_label: Metadata
slug: /user/metadata
---

```mdx-code-block
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';
```

Returns the metadata associated with a user.

### URL

`GET https://api.synodic.ai/{user}`

### Path Parameters

- **\{user\}**: username (string) or Firebase UID (string)

### Example Request

<Tabs>
<TabItem value="Bash">

```bash
curl -X GET "https://api.synodic.ai/{user}"
```

</TabItem>
<TabItem value="Python">

```python
import requests

response = requests.get("https://api.synodic.ai/{user}")
print(response.json())
```

</TabItem>
<TabItem value="Node.js">

```javascript
const axios = require('axios');

axios.get("https://api.synodic.ai/{user}")
    .then(response => {
        console.log(response.data);
    })
    .catch(error => {
        console.error(error);
    });
```

</TabItem>
<TabItem value="Rust">

```rust
use reqwest;

fn main() {
    let response = reqwest::blocking::get("https://api.synodic.ai/{user}")
        .expect("Failed to send request");
        
    println!("{:?}", response.text());
}
```

</TabItem>
</Tabs>

### Example Response

<Tabs>
<TabItem value="User Metadata">
```json
{
    "created_at": 1716899295,
    "username": "example",
    "display_name": "Example",
    "photo_url": "https://synodic-profile.s3.amazonaws.com/lowoyylw.png",
    "repositories": ["example/coffee", "example/cars"],
    "autotrain_units": 150,
    "autolabel_images": 495,
    "inference_frames": 45903,
    "models_trained": 2,
    "payment_details": true
}
```
</TabItem>
<TabItem value="Other User Metadata">
```json
{
    "created_at": 1716899295,
    "username": "example",
    "display_name": "Example",
    "photo_url": "https://synodic-profile.s3.amazonaws.com/lowoyylw.png",
    "repositories": ["example/coffee", "example/cars"]
}
```
</TabItem>
<TabItem value="Error">
```json
{
    "error": "User not found"
}
```
</TabItem>
</Tabs>

