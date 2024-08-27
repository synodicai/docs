---
id: repository-init
title: Repository Init
sidebar_label: Initalize
slug: /repository/init
---

```mdx-code-block
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';
```

Creates a new repository.

### URL

`POST https://api.synodic.ai/v0/{user}/{repo}/init`

### Headers

- **x-api-key**: `YOUR_API_KEY` (string)

### Path Parameters

- **\{user\}**: username (string)
- **\{repo\}**: repository name (string)

### Example Request

<Tabs>
<TabItem value="Bash">

```bash
curl -X POST "https://api.synodic.ai/v0/{user}/{repo}/init" -H "x-api-key: YOUR_API_KEY"
```

</TabItem>
<TabItem value="Python">

```python
import requests

headers = {
    "x-api-key": "YOUR_API_KEY"
}

response = requests.post("https://api.synodic.ai/v0/{user}/{repo}/init", headers=headers)
print(response.json())
```

</TabItem>
<TabItem value="Node.js">

```javascript
const axios = require('axios');

const headers = {
    "x-api-key": "YOUR_API_KEY"
};

axios.post("https://api.synodic.ai/v0/{user}/{repo}/init", { headers })
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
    let response = client.post("https://api.synodic.ai/v0/{user}/{repo}/init")
        .header("x-api-key", "YOUR_API_KEY")
        .send()
        .expect("Failed to send request");
        
    println!("{:?}", response.text());
}
```

</TabItem>
</Tabs>

### Example Response

`Status 200 OK`