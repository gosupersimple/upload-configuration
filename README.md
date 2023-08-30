This repository provides action to upload Supersimple configuration file.

## Usage

```yaml
name: Upload Configuration to Supersimple

on:
  push:
    branches:
      - main

jobs:
  upload:
    name: Upload to Supersimple

    runs-on: ubuntu-latest

    steps:
      - uses: actions/checkout@v2

      - uses: gosupersimple/upload-configuration@v2
        with:
          account_id: ${{ vars.SUPERSIMPLE_ACCOUNT_ID }}
          token: ${{ secrets.SUPERSIMPLE_TOKEN }}
          config_file: configuration.yaml
```
