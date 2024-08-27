---
id: class-add
title: Class Add
sidebar_label: Add
slug: /class/add
---

```mdx-code-block
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';
```


Adds a class to a repository.


### URL

`POST https://api.synodic.ai/v0/{user}/{repo}/class/add`

### Headers

- **x-api-key**: `YOUR_API_KEY` (string)

### Path Parameters

- **\{user\}**: username (string)
- **\{repo\}**: repository name (string)

### Body

- **class**: class name (string)

### Example Request

<Tabs>
<TabItem value="Bash">

```bash
curl -X POST "https://api.synodic.ai/v0/{user}/{repo}/class/add" -H "x-api-key: YOUR_API_KEY" -H "Content-Type: application/json" -d '{"class": "class_name"}'
```

</TabItem>
<TabItem value="Python">

```python
import requests

headers = {
    "x-api-key": "YOUR_API_KEY"
}

response = requests.post("https://api.synodic.ai/v0/{user}/{repo}/class/add", headers=headers, json={"class": "class_name"})
print(response.json())
```

</TabItem>
<TabItem value="Node.js">

```javascript
const axios = require('axios');

const headers = {
    "x-api-key": "YOUR_API_KEY"
};

axios.post("https://api.synodic.ai/v0/{user}/{repo}/class/add", { class: "class_name" }, { headers })
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
    let response = client.post("https://api.synodic.ai/v0/{user}/{repo}/class/add")
        .header("x-api-key", "YOUR_API_KEY")
        .json(&serde_json::json!({ "class": "class_name" }))
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
        "Existing Class 1",
        "New Class"
    ]
}