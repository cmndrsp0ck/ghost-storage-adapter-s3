# Ghost storage adapter S3

An AWS S3 storage adapter for Ghost 1.x

For Ghost 0.10.x and 0.11.x support check out
[Ghost storage adapter s3 v1.3.0](https://github.com/colinmeinke/ghost-storage-adapter-s3/releases/tag/v1.3.0).

## Installation

### Option A

```shell
npm install ghost-storage-adapter-do
mkdir -p ./content/adapters/storage
cp -r ./node_modules/ghost-storage-adapter-do ./content/adapters/storage/s3
```
### Option B

This option will allow you to keep the module within your *node_modules* directory.

```shell
npm install ghost-storage-adapter-do
mkdir -p ./content/adapters/storage/s3
cat << _EOF_ > ./content/adapters/storage/s3/index.js
'use strict'
module.exports = require('ghost-storage-adapter-do');
_EOF_

```

## Configuration

```json
"storage": {
  "active": "s3",
  "s3": {
    "accessKeyId": "YOUR_ACCESS_KEY_ID",
    "assetHost": "YOUR_OPTIONAL_CDN_URL",
    "bucket": "YOUR_BUCKET_NAME",
    "pathPrefix": "YOUR_OPTIONAL_BUCKET_SUBDIRECTORY",
    "region": "YOUR_REGION_SLUG",
    "secretAccessKey": "YOUR_SECRET_ACCESS_KEY",
    "endpoint": "YOUR_OPTIONAL_ENDPOINT_URL (Required for 3rd party S3 providers)"
  }
}
```

### Via environment variables

```
AWS_ACCESS_KEY_ID
AWS_SECRET_ACCESS_KEY
AWS_DEFAULT_REGION
GHOST_STORAGE_ADAPTER_S3_PATH_BUCKET
GHOST_STORAGE_ADAPTER_S3_ASSET_HOST  // optional
GHOST_STORAGE_ADAPTER_S3_PATH_PREFIX // optional
GHOST_STORAGE_ADAPTER_S3_ENDPOINT // required for usage on DigitalOcean
```

## License

[ISC](./LICENSE.md).
