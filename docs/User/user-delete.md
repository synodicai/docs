---
id: user-delete
title: User Delete
sidebar_label: Delete
slug: /user/delete
---

```mdx-code-block
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';
```

Permanently deletes all user data.

### URL

`DELETE https://api.synodic.ai/{user}`

### Path Parameters

- **\{user\}**: username (string) or Firebase UID (string)

### Example Request

<Tabs>
<TabItem value="Bash">

```bash
curl -X DELETE "https://api.synodic.ai/{user}"
```

</TabItem>
<TabItem value="Python">

```python
import requests

response = requests.delete("https://api.synodic.ai/{user}")
print(response.status_code)
```

</TabItem>
<TabItem value="Node.js">

```javascript
const axios = require('axios');

axios.delete("https://api.synodic.ai/{user}")
    .then(response => {
        console.log(response.status);
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
    let response = reqwest::blocking::delete("https://api.synodic.ai/{user}")
        .expect("Failed to send request");
        
    println!("{:?}", response.status());
}
```

</TabItem>
</Tabs>

### Example Response

`200 SUCCESS`