---
id: download-dataset
title: Download Dataset
sidebar_label: Download Dataset
slug: /download/dataset
---

```mdx-code-block
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';
```


Downloads the dataset from a repository.


### URL

`GET https://api.synodic.ai/v0/{user}/{repo}/download/dataset`

### Headers

- **x-api-key**: `YOUR_API_KEY` (string)

### Path Parameters

- **\{user\}**: username (string)
- **\{repo\}**: repository name (string)

### Query Parameters

- **format**: format (string)
- **train_percent**: train percent (integer)
- **test_percent**: test percent (integer)
- **valid_percent**: valid percent (integer)

### Example Request

<Tabs>
<TabItem value="Python">

```python
import requests

headers = {
    "x-api-key": "YOUR_API_KEY"
}

params = {
    "format": "yolo",
    "train_percent": 70,
    "test_percent": 20,
    "valid_percent": 10
}

download_json = {}
while 'url' not in download_json:
    download_json = requests.get("https://api.synodic.ai/v0/{user}/{repo}/download/dataset", headers=headers, params=params)
    time.sleep(0.5)

with open("dataset.zip", "wb") as file:
    file.write(requests.get(download_json['url']).content)
```

</TabItem>
<TabItem value="Node.js">

```javascript
const axios = require('axios');
const fs = require('fs');

const headers = {
  'x-api-key': 'YOUR_API_KEY'
};

const params = {
  format: 'yolo',
  train_percent: 70,
  test_percent: 20,
  valid_percent: 10
};

async function downloadDataset() {
  let downloadJson = {};
  while (!downloadJson.url) {
    const response = await axios.get('https://api.synodic.ai/v0/{user}/{repo}/download/dataset', { headers, params });
    downloadJson = response.data;
    if (!downloadJson.url) {
      await new Promise(resolve => setTimeout(resolve, 500));
    }
  }
  const fileResponse = await axios.get(downloadJson.url, { responseType: 'arraybuffer' });
  fs.writeFileSync('dataset.zip', fileResponse.data);
}

downloadDataset();
```

</TabItem>
<TabItem value="Rust">

```rust
use reqwest::header::{HeaderMap, HeaderValue};
use std::fs::File;
use std::io::Write;
use std::thread::sleep;
use std::time::Duration;

#[tokio::main]
async fn main() -> Result<(), Box<dyn std::error::Error>> {
    let mut headers = HeaderMap::new();
    headers.insert("x-api-key", HeaderValue::from_static("YOUR_API_KEY"));
    
    let client = reqwest::Client::new();
    let mut download_json = serde_json::Value::Null;
    
    while !download_json.get("url").is_some() {
        let response = client
            .get("https://api.synodic.ai/v0/{user}/{repo}/download/dataset")
            .headers(headers.clone())
            .query(&[
                ("format", "yolo"),
                ("train_percent", "70"),
                ("test_percent", "20"),
                ("valid_percent", "10"),
            ])
            .send()
            .await?;
        
        download_json = response.json().await?;
        
        if !download_json.get("url").is_some() {
            sleep(Duration::from_millis(500));
        }
    }
    
    let url = download_json["url"].as_str().unwrap();
    let dataset = client.get(url).send().await?.bytes().await?;
    
    let mut file = File::create("dataset.zip")?;
    file.write_all(&dataset)?;
    
    Ok(())
}
```

</TabItem>
</Tabs>