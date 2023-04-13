To build:
cannot build two architectures at the same time because of the precompiled libraries of segwayrmp.

Build command:
docker buildx create --name mybuilder
docker buildx use mybuilder
export DOCKER_CLI_EXPERIMENTAL=enabled

docker buildx build --platform linux/amd64 --build-arg GHCR_TOKEN=<your_token> -f ./dockerfile.amd64 -t ghcr.io/bjoernellens1/ros:humble-amd64 .

or
docker buildx build --platform linux/arm64 --build-arg GHCR_TOKEN=<your_token> -f ./dockerfile.arm64 -t ghcr.io/bjoernellens1/ros:humble-arm64 .

docker buildx build --platform linux/arm64 --build-arg GHCR_TOKEN=<your_token> -f ./dockerfile.arm64 -t ghcr.io/bjoernellens1/ros:humble-arm64 . --push
