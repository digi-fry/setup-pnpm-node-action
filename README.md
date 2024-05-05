# Setup PNPM and Node.js Action

This GitHub Action sets up a specific version of Node.js and PNPM, installs dependencies, and sets up a cache for PNPM.

## Usage

```yaml
- uses: digi-fry/setup-pnpm-node-action@v1
  with:
    node-version: '20'
    pnpm-version: '9'
```

## Inputs

* `node-version`: (Required) The version of Node.js to use. This should be a valid Node.js version.
* `pnpm-version`: (Required) The version of PNPM to use. This should be a valid PNPM version.

## Outputs

None

## Example

```yaml
name: My Workflow CI

on:
  push:
    branches:
      - main
  pull_request:
    types:
      - opened
      - reopened
      - synchronize

env:
  NODE_VERSION: 20
  PNPM_VERSION: 9

jobs:
  cache-and-install:
    runs-on: ubuntu-latest

    name: Setup Cache and Install Dependencies

    steps:
      - name: Setup Cache and Install Dependencies
        uses: digi-fry/setup-pnpm-node-action@v1
        with:
          node-version: ${{ env.NODE_VERSION }}
          pnpm-version: ${{ env.PNPM_VERSION }}
```

## License

[MIT](LICENSE)

