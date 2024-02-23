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
      - uses: actions/checkout@v3

      - uses: gosupersimple/upload-configuration@v2.6.1
        with:
          account_id: ${{ vars.SUPERSIMPLE_ACCOUNT_ID }}
          token: ${{ secrets.SUPERSIMPLE_TOKEN }}
          config_file: configuration.yaml
```

## Action Inputs

### `account_id`

**Required.** Supersimple account ID where to import configuration to. Obtain it from Supersimple app in "Account Settings" page.

### `token`

**Required.** Supersimple API token. It is recommended to store this as `SUPERSIMPLE_TOKEN` secret in GitHub. Obtain the token from Supersimple app in "Account Settings" page.

### `config_file`

**Optional.** Defaults to `supersimple.yaml` but should point to YAML file in repository. Please note that this file is also being validated against the JSON schema before the import.
