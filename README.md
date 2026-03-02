# hasura-dev-assets

Release assets for Docker-free local Hasura development runtime.

This repository publishes:

- `graphql-engine-darwin-arm64.tar.gz` (self-contained bundle with `graphql-engine` + dylibs)
- `manifest.json`
- `checksums.txt`

The CLI resolves engine binaries from:

`https://github.com/faisalil/hasura-dev-assets/releases/download/<tag>/manifest.json`

## Manifest contract

`manifest.json` follows:

```json
{
  "version": "v2.48.12",
  "assets": {
    "darwin-arm64": {
      "url": "https://github.com/faisalil/hasura-dev-assets/releases/download/v2.48.12/graphql-engine-darwin-arm64.tar.gz",
      "sha256": "<sha256>"
    }
  }
}
```

## Workflows

- `publish-engine-darwin.yml`: builds `graphql-engine` for darwin-arm64 from `hasura/graphql-engine` and publishes release assets.
- `publish-engine-manifest.yml`: publishes/updates manifest + checksums for a release tag.
