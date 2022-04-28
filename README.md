# github-action-build-and-push-to-ghcr

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
      docker_image_repository: ghcr.io/user/image_repository
    secrets:
      GITHUB_PAT: ${{ secrets.GITHUB_PAT }}
```

