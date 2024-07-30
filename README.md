# Docker

A collection of docker based projects.

All docker images should be built for multiple platforms:

```bash
docker buildx create --use default
docker buildx build \
    --push \
    --platform linux/arm64/v8,linux/arm/v7,linux/amd64 \
    --tag muxelmann/${PROJECT_NAME} \
    .
```