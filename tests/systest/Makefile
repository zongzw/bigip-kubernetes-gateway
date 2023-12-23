linux:
	rm -f bigip-k8s.test; \
	CGO_ENABLED=0 GOOS=linux GOARCH=amd64 ginkgo build . -o bigip-k8s.test

darwin:
	rm -f bigip-k8s.test; \
	CGO_ENABLED=0 GOOS=darwin GOARCH=amd64 ginkgo build . -o bigip-k8s.test
