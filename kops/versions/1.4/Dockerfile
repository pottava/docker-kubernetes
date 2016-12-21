# kops v1.4
# docker run --rm pottava/kops version
# docker run --rm -e AWS_ACCESS_KEY_ID -e AWS_SECRET_ACCESS_KEY -e KOPS_STATE_STORE \
#        -v `pwd`/out:/out -v `pwd`/id_rsa.pub:/tmp/id_rsa.pub \
#        pottava/kops create cluster --target=terraform --ssh-public-key=/tmp/id_rsa.pub $CLUSTER_NAME
# docker run --rm -e AWS_ACCESS_KEY_ID -e AWS_SECRET_ACCESS_KEY -e KOPS_STATE_STORE pottava/kops edit cluster $CLUSTER_NAME

FROM alpine:3.4

ENV KOP_VERSION=1.4.4

RUN apk --no-cache add --virtual build-dependencies curl \
  && apk --no-cache add ca-certificates  \
  && curl -O --location --silent --show-error https://github.com/kubernetes/kops/releases/download/v$KOP_VERSION/kops-linux-amd64 \
  && mv kops-linux-amd64 /usr/bin/kops \
  && chmod +x /usr/bin/kops \
  && apk del --purge build-dependencies

ENTRYPOINT ["/usr/bin/kops"]
CMD ["--help"]
