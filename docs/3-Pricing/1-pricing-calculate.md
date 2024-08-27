---
id: pricing-calculate
title: Pricing Calculate
sidebar_label: Calculate
slug: /pricing/calculate
---

```mdx-code-block
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';
```

Calculates the price to autotrain a model based on the specified configuration.

### URL

`GET https://api.synodic.ai/v0/pricing/calculate`

### Query Parameters

- **\{gpu\}**: `t4 | a100 | h100` (string)
- **\{variant\}**: the type of model being trained (string)
  - `yolov6n`, `yolov6s`, `yolov6m`, `yolov6l` (YOLOv6 variants)
  - `yolov8n`, `yolov8s`, `yolov8m`, `yolov8l`, `yolov8x` (YOLOv8 variants)
  - `yolov9t`, `yolov9s`, `yolov9m`, `yolov9c`, `yolov9e` (YOLOv9 variants)
  - `yolov10n`, `yolov10s`, `yolov10m`, `yolov10l`, `yolov10x` (YOLOv10 variants)
- **\{epochs\}**: (integer)
- **\{train_images\}**: the number of images in the training set (integer)
- **\{test_images\}**: the number of images in the test set (integer)
- **\{valid_images\}**: the number of images in the validation set (integer)

### Example Request

<Tabs>
<TabItem value="Bash">

```bash
curl -X GET "https://api.synodic.ai/v0/pricing/calculate?gpu={gpu}&variant={variant}&epochs={epochs}&train_images={train_images}&test_images={test_images}&valid_images={valid_images}"
```

</TabItem>
<TabItem value="Python">

```python
import requests

params = {
    "gpu": "{gpu}",
    "variant": "{variant}",
    "epochs": "{epochs}",
    "train_images": "{train_images}",
    "test_images": "{test_images}",
    "valid_images": "{valid_images}"
}

response = requests.get("https://api.synodic.ai/v0/pricing/calculate", params=params)
print(response.json())
```

</TabItem>
<TabItem value="Node.js">

```javascript
const axios = require('axios');

const params = {
    gpu: '{gpu}',
    variant: '{variant}',
    epochs: '{epochs}',
    train_images: '{train_images}',
    test_images: '{test_images}',
    valid_images: '{valid_images}'
};

axios.get("https://api.synodic.ai/v0/pricing/calculate", { params })
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
    let params = [
        ("gpu", "{gpu}"),
        ("variant", "{variant}"),
        ("epochs", "{epochs}"),
        ("train_images", "{train_images}"),
        ("test_images", "{test_images}"),
        ("valid_images", "{valid_images}")
    ];
    let response = client.get("https://api.synodic.ai/v0/pricing/calculate")
        .query(&params)
        .send()
        .expect("Failed to send request");
        
    println!("{:?}", response.text().expect("Failed to read response text"));
}
```

</TabItem>
</Tabs>

### Example Response

```json
{
    "cost": 0.9198558427008771,
    "time": 316.28281124385455,
    "prediction": "linear_regression"
}
```
