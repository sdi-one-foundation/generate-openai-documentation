# generate-openai-documentation
A composite Github Action to automatically generate OpenAI Documentation for Single Digits services in the sdi-one-architecture repostory named centralized-openapi-specs.

Example release.yaml that uses this action:

```yaml
name: Release

on:
  release:
    types: [published]

jobs:
  release:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout
        uses: actions/checkout@v2

      - name: Publish OpenAI Documentation
        uses: sdi-one-foundation/generate-openai-documentation@v1
        with:
          service-name: ${{ github.repository }}
          team-name: ${{ github.repository_owner }}
          file-output-path: "target/generated-api/service-name.openapi.json"
```
