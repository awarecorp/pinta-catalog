# pinta-catalog seed

This directory contains the initial content for the `awarecorp/pinta-catalog` GitHub repository.

## Setup

1. Create private GitHub repository `awarecorp/pinta-catalog`.
2. Clone it locally.
3. Copy this directory's contents into the repo.
4. Replace the `sha256` fields in `catalog/index.json` and `catalog/mcp-logger/1.0.0.yaml`
   with the actual SHA-256 of the mcp-logger tarball you're pointing to (see "Computing sha256" below).
5. Commit and push.

The manager will fetch from:
`https://raw.githubusercontent.com/awarecorp/pinta-catalog/main/catalog/index.json`

## Computing sha256

```bash
curl -L -o /tmp/mcp-logger.tgz https://registry.npmjs.org/@awarecorp/mcp-logger/-/mcp-logger-<version>.tgz
shasum -a 256 /tmp/mcp-logger.tgz
```

## Local dev — point manager to a local catalog

```bash
PINTA_CATALOG_URL=file:///path/to/pinta-catalog-seed/catalog/index.json npm run tauri:dev
```
