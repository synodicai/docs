---
id: repository-metadata
title: Repository Metadata
sidebar_label: Metadata
slug: /repository/metadata
---

```mdx-code-block
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';
```

Returns the metadata associated with a repository.

### URL

`GET https://api.synodic.ai/v0/{user}/{repo}`

### Headers

- **x-api-key**: `YOUR_API_KEY` (string, optional)

### Path Parameters

- **\{user\}**: username (string)
- **\{repo\}**: repository name (string)

### Example Request

<Tabs>
<TabItem value="Bash">

```bash
curl -X GET "https://api.synodic.ai/v0/{user}/{repo}" -H "x-api-key: YOUR_API_KEY"
```

</TabItem>
<TabItem value="Python">

```python
import requests

headers = {
    "x-api-key": "YOUR_API_KEY"
}

response = requests.get("https://api.synodic.ai/v0/{user}/{repo}", headers=headers)
print(response.json())
```

</TabItem>
<TabItem value="Node.js">

```javascript
const axios = require('axios');

const headers = {
    "x-api-key": "YOUR_API_KEY"
};

axios.get("https://api.synodic.ai/v0/{user}/{repo}", { headers })
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
    let response = client.get("https://api.synodic.ai/v0/{user}/{repo}")
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
  "classes": [
    "apple",
    "banana"
  ],
  "description": "Detecting apples and bananas",
  "images": [
    "synodic.31086ot9.0Es1A1oo.jpg",
    "synodic.EW2295A7.WR169wL7.jpg",
    "synodic.Agm8l275.c16Q6988.jpg",
    "synodic.w2847B01.493NW7s0.jpg",
  ],
  "models": [
    "fx0MVR",
    "p8kHuG",
    "4qPEam",
  ]
}
```
