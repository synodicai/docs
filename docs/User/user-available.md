---
id: user-available
title: User Available
sidebar_label: Available
slug: /user/available
---

```mdx-code-block
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';
```

Checks if the username is available or already taken.


### URL

`GET https://api.synodic.ai/{user}/available`

### Path Parameters

- **\{user\}**: username (string)

### Example Request

<Tabs>
<TabItem value="Bash">

```bash
curl -X GET "https://api.synodic.ai/{user}/available"
```

</TabItem>
<TabItem value="Python">

```python
import requests

response = requests.get("https://api.synodic.ai/{user}/available")
print(response.json())
```

</TabItem>
<TabItem value="Node.js">

```javascript
const axios = require('axios');

axios.get("https://api.synodic.ai/{user}/available")
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
    let response = reqwest::blocking::get("https://api.synodic.ai/{user}/available")
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