update:
	rm -fr node_modules package-lock.json
	npm version
	npm install --save --save-exact
	rm -fr node_modules

build-init:
	docker buildx create --driver=docker-container --name=ferretdb-deps

build-local:
	rm -fr node_modules
	docker buildx build --builder=ferretdb-deps \
		--tag=docusaurus-docs-local \
		--load .

build-push:
	rm -fr node_modules
	test -n $(DOCKER_TAG)
	docker buildx build --builder=ferretdb-deps \
		--platform=linux/arm64,linux/amd64 \
		--tag=ghcr.io/ferretdb/docusaurus-docs:$(DOCKER_TAG) \
		--push .
