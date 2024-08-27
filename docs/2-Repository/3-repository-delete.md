---
id: repository-delete
title: Repository Delete
sidebar_label: Delete
slug: /repository/delete
---

```mdx-code-block
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';
```


Deletes a repository.


### URL

`DELETE https://api.synodic.ai/v0/{user}/{repo}`

### Headers

- **x-api-key**: `YOUR_API_KEY` (string)

### Path Parameters

- **\{user\}**: username (string)
- **\{repo\}**: repository name (string)

### Example Request

<Tabs>
<TabItem value="Bash">

```bash
curl -X DELETE "https://api.synodic.ai/v0/{user}/{repo}" -H "x-api-key: YOUR_API_KEY"
```

</TabItem>
<TabItem value="Python">

```python
import requests

headers = {
    "x-api-key": "YOUR_API_KEY"
}

response = requests.delete("https://api.synodic.ai/v0/{user}/{repo}", headers=headers)
print(response.json())
```

</TabItem>
<TabItem value="Node.js">

```javascript
const axios = require('axios');

const headers = {
    "x-api-key": "YOUR_API_KEY"
};

axios.delete("https://api.synodic.ai/v0/{user}/{repo}", { headers })
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
    let response = client.delete("https://api.synodic.ai/v0/{user}/{repo}")
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