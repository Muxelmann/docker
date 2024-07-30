# PrivateGPT

This dockerfile makes a container to run [zylon-ai/private-gpt](https://github.com/zylon-ai/private-gpt/tree/main) in a way that connects it to [ollama/ollama](https://github.com/ollama/ollama).

Here, Ollama should run in a container on the same docker network to make it reachable by the PrivateGPT container. E.g., if the container's name is `ollama`, then the following environment variable can be left unchanged:

```
OLLAMA_BASE_URL="http://ollama:11434"
``` 

Otherwise, specify the correct URL applicable to your scenario.

To store the embedded data outside the container link a volume to:

```
/home/worker/app/local_data/
```

There is also a `models` folder, but it is not used when connecting to a remote Ollama instance.

## Build

This image was build for `linux/arm64` and `linux/amd64`.

```bash
docker buildx build --push --platform linux/arm64/v8,linux/amd64 --tag muxelmann/privategpt .
```
