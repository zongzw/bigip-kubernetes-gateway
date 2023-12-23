# docker build -t bigip-kubernetes-gateway-webhook:latest -f build/Dockerfile .
FROM alpine:3.16.2

COPY ./bigip-kubernetes-gateway-webhook-linux /

RUN date > /build_date