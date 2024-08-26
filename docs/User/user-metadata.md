---
id: user-metadata
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

`GET https://api.synodic.ai/v0/{user}`

### Headers

- **x-api-key**: `YOUR_API_KEY` (string, optional)

### Path Parameters

- **\{user\}**: username (string)

### Example Request

<Tabs>
<TabItem value="Bash">

```bash
curl -X GET "https://api.synodic.ai/v0/{user}" -H "x-api-key: YOUR_API_KEY"
```

</TabItem>
<TabItem value="Python">

```python
import requests

headers = {
    "x-api-key": "YOUR_API_KEY"
}

response = requests.get("https://api.synodic.ai/v0/{user}", headers=headers)
print(response.json())
```

</TabItem>
<TabItem value="Node.js">

```javascript
const axios = require('axios');

const headers = {
    "x-api-key": "YOUR_API_KEY"
};

axios.get("https://api.synodic.ai/v0/{user}", { headers })
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
    let client = reqwest::blocking::Client::new();
    let response = client.get("https://api.synodic.ai/v0/{user}")
        .header("x-api-key", "YOUR_API_KEY")
        .send()
        .expect("Failed to send request");
        
    println!("{:?}", response.text());
}
```

</TabItem>
</Tabs>

### Example Response

<Tabs>
<TabItem value="Current User Metadata">
```json
{
    "created_at": 1716899295,
    "photo_url": "https://synodic-profile.s3.amazonaws.com/lowoyylw.png",
    "repositories": ["example/coffee", "example/cars"],
    "autotrain_units": 150,
    "autolabel_images": 495,
    "inference_frames": 45903,
    "models_trained": 2,
    "payment_details": true,
    "plan": "pay-as-you-go"
}
```
</TabItem>
<TabItem value="Other User's Metadata">
```json
{
    "created_at": 1716899295,
    "photo_url": "https://synodic-profile.s3.amazonaws.com/lowoyylw.png",
    "repositories": ["example/coffee", "example/cars"]
}
```
</TabItem>
</Tabs>
