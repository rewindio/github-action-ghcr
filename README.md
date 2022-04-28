# github-action-build-and-push

This is a reusable workflow that builds and pushes images to a container registry.

## Example usage

```yaml
name: Build

on:
  push:

jobs:
  build-and-push:
    name: "Build & Push"
    uses: rewindio/github-actions-build-and-push/.github/workflows/build-and-push.yml@v0
    with:
      docker_file_path: ./Dockerfile
      docker_target: production
      external_registry: ghcr.io
    secrets:
      REG_USERNAME: ${{ secrets.REG_USERNAME }}
      REG_PW: ${{ secrets.REG_PW }}
```

