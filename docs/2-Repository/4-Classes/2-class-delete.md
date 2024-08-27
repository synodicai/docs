---
id: class-delete
title: Class Delete
sidebar_label: Delete
slug: /class/delete
---

```mdx-code-block
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';
```


Deletes a class from a repository.


### URL

`POST https://api.synodic.ai/v0/{user}/{repo}/class/delete`

### Headers

- **x-api-key**: `YOUR_API_KEY` (string)

### Path Parameters

- **\{user\}**: username (string)
- **\{repo\}**: repository name (string)

### Body

- **index**: class index (integer)

### Example Request

<Tabs>
<TabItem value="Bash">

```bash
curl -X POST "https://api.synodic.ai/v0/{user}/{repo}/class/delete" -H "x-api-key: YOUR_API_KEY" -H "Content-Type: application/json" -d '{"index": 0}'
```

</TabItem>
<TabItem value="Python">

```python
import requests

headers = {
    "x-api-key": "YOUR_API_KEY"
}

response = requests.post("https://api.synodic.ai/v0/{user}/{repo}/class/delete", headers=headers, json={"index": 0})
print(response.json())
```

</TabItem>
<TabItem value="Node.js">

```javascript
const axios = require('axios');

const headers = {
    "x-api-key": "YOUR_API_KEY"
};

axios.post("https://api.synodic.ai/v0/{user}/{repo}/class/delete", { index: 0 }, { headers })
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
    let response = client.post("https://api.synodic.ai/v0/{user}/{repo}/class/delete")
        .header("x-api-key", "YOUR_API_KEY")
        .json(&serde_json::json!({ "index": 0 }))
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
        "Existing Class 0",
        "Existing Class 1"
    ]
}