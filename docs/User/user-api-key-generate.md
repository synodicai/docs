---
id: user-api-key-generate
title: Generate a new API Key
sidebar_label: API Key Generate
slug: /user/api-key-generate
---

```mdx-code-block
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';
```

Generates an api key for the specified user.

### URL

`GET https://api.synodic.ai/v0/{user}/api-key-generate`

### Headers

- **x-api-key**: `YOUR_API_KEY` (string)

### Path Parameters

- **\{user\}**: username (string)

### Example Request

<Tabs>
<TabItem value="Bash">

```bash
curl -X GET "https://api.synodic.ai/v0/{user}/api-key-generate" -H "x-api-key: YOUR_API_KEY"
```

</TabItem>
<TabItem value="Python">

```python
import requests

headers = {
    "x-api-key": "YOUR_API_KEY"
}

response = requests.get("https://api.synodic.ai/v0/{user}/api-key-generate", headers=headers)
print(response.json())
```

</TabItem>
<TabItem value="Node.js">

```javascript
const axios = require('axios');

const headers = {
    "x-api-key": "YOUR_API_KEY"
};

axios.get("https://api.synodic.ai/v0/{user}/api-key-generate", { headers })
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
    let response = client.get("https://api.synodic.ai/v0/{user}/api-key-generate")
        .header("x-api-key", "YOUR_API_KEY")
        .send()
        .expect("Failed to send request");
        
    println!("{:?}", response.text());
}
```

</TabItem>
</Tabs>

### Example Response

```json
{
    "api_key": "AErhF3kYnuxqYAHHjEizoOpEWWSxYprNMvBGGSc1"
}
```