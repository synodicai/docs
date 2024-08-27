---
id: pricing-average
title: Pricing Average
sidebar_label: Average
slug: /pricing/average
---

```mdx-code-block
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';
```

Returns the average cost and training time of an autotrained model.

### URL

`GET https://api.synodic.ai/v0/pricing/average`

### Example Request

<Tabs>
<TabItem value="Bash">

```bash
curl -X GET "https://api.synodic.ai/v0/pricing/average"
```

</TabItem>
<TabItem value="Python">

```python
import requests

response = requests.get("https://api.synodic.ai/v0/pricing/average")
print(response.json())
```

</TabItem>
<TabItem value="Node.js">

```javascript
const axios = require('axios');

axios.get("https://api.synodic.ai/v0/pricing/average")
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
    let response = client.get("https://api.synodic.ai/v0/pricing/average")
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
    "average_cost": 2.5446468611850963,
    "average_time": 1520.5537514615387
}
```