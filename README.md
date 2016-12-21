kubernetes-related tools
---

## kops

### Images

https://hub.docker.com/r/pottava/kops/

### Available Tags

https://hub.docker.com/r/pottava/kops/tags/

### Supported tags and respective `Dockerfile` links

・latest ([versions/1.4/Dockerfile](https://github.com/pottava/docker-kubernetes/blob/master/kops/versions/1.4/Dockerfile))  
・1.4 ([versions/1.4/Dockerfile](https://github.com/pottava/docker-kubernetes/blob/master/kops/versions/1.4/Dockerfile))  

### Usage

```
docker run --rm pottava/kops version
docker run --rm -e AWS_ACCESS_KEY_ID -e AWS_SECRET_ACCESS_KEY -e KOPS_STATE_STORE \
    -v `pwd`/out:/out -v `pwd`/id_rsa.pub:/tmp/id_rsa.pub \
    pottava/kops create cluster --target=terraform --ssh-public-key=/tmp/id_rsa.pub $CLUSTER_NAME
docker run --rm -it -e AWS_ACCESS_KEY_ID -e AWS_SECRET_ACCESS_KEY -e KOPS_STATE_STORE \
    pottava/kops edit cluster $CLUSTER_NAME
```
