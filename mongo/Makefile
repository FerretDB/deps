default: build-local

build-init:
	docker buildx create --driver=docker-container --name=ferretdb

build-local:
	docker buildx build --builder=ferretdb \
		--tag=mongo-local \
		--load .

build-push:
	test -n $(DOCKER_TAG)
	docker buildx build --builder=ferretdb \
		--platform=linux/amd64 \
		--tag=ghcr.io/ferretdb/mongo:$(DOCKER_TAG) \
		--push .
