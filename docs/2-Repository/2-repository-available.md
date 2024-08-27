---
id: repository-available
title: Repository Available
sidebar_label: Available
slug: /repository/available
---

```mdx-code-block
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';
```


Checks if the repository name is available or already taken.


### URL

`GET https://api.synodic.ai/v0/{user}/{repo}/available`

### Headers

- **x-api-key**: `YOUR_API_KEY` (string, optional)

### Path Parameters

- **\{user\}**: username (string)
- **\{repo\}**: repository name (string)

### Example Request

<Tabs>
<TabItem value="Bash">

```bash
curl -X GET "https://api.synodic.ai/v0/{user}/{repo}/available" -H "x-api-key: YOUR_API_KEY"
```

</TabItem>
<TabItem value="Python">

```python
import requests

headers = {
    "x-api-key": "YOUR_API_KEY"
}

response = requests.get("https://api.synodic.ai/v0/{user}/{repo}/available", headers=headers)
print(response.json())
```

</TabItem>
<TabItem value="Node.js">

```javascript
const axios = require('axios');

const headers = {
    "x-api-key": "YOUR_API_KEY"
};

axios.get("https://api.synodic.ai/v0/{user}/{repo}/available", { headers })
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
    let response = client.get("https://api.synodic.ai/v0/{user}/{repo}/available")
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
    "available": true
}
```