all: upload

dstamp = $(shell date +%Y%m%d)
tstamp = $(shell date +%H%M%S)
timestamp ?= ${dstamp}-${tstamp}
version ?= latest
docker_repo ?= zongzw/bigip-kubernetes-gateway-webhook
release_repo ?= f5devcentral/bigip-kubernetes-gateway-webhook

image_name := ${docker_repo}:${version}-${timestamp}

upload: image
	docker push ${image_name}
	docker tag ${image_name} ${release_repo}:${version}-${dstamp}

image: binary
	docker buildx build --no-cache -t ${image_name}  .

binary:
	cd ../../cmd/webhook; \
	CGO_ENABLED=0 GOOS=linux GOARCH=amd64 \
	go build -ldflags '-s -w --extldflags "-static -fpic"' -o ../../build/webhook/bigip-kubernetes-gateway-webhook-linux; \
	# CGO_ENABLED=0 GOOS=darwin GOARCH=amd64 \
	# go build -ldflags '-s -w --extldflags "-static -fpic"' -o ../../build/webhook/bigip-kubernetes-gateway-webhook-darwin