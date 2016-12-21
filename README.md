kubernetes-related tools
---

## kubectl

### Images

https://hub.docker.com/r/pottava/kubectl/

### Available Tags

https://hub.docker.com/r/pottava/kubectl/tags/

### Supported tags and respective `Dockerfile` links

・latest ([kubectl/versions/1.5/Dockerfile](https://github.com/pottava/docker-kubernetes/blob/master/kubectl/versions/1.5/Dockerfile))  
・1.5 ([kubectl/versions/1.5/Dockerfile](https://github.com/pottava/docker-kubernetes/blob/master/kubectl/versions/1.5/Dockerfile))  

### Usage

```
alias kubectl="docker run --rm -it -v $HOME/.kube/:/root/.kube/ pottava/kubectl"
kubectl version
kubectl get pods
```

## kops

### Images

https://hub.docker.com/r/pottava/kops/

### Available Tags

https://hub.docker.com/r/pottava/kops/tags/

### Supported tags and respective `Dockerfile` links

・latest ([kops/versions/1.4/Dockerfile](https://github.com/pottava/docker-kubernetes/blob/master/kops/versions/1.4/Dockerfile))  
・1.4 ([kops/versions/1.4/Dockerfile](https://github.com/pottava/docker-kubernetes/blob/master/kops/versions/1.4/Dockerfile))  

### Usage

```
alias kops="docker run --rm -it -e AWS_ACCESS_KEY_ID -e AWS_SECRET_ACCESS_KEY -e AWS_DEFAULT_REGION -e KOPS_STATE_STORE pottava/kops"
kops version

export CLUSTER_NAME=my-cluster.k8s.com
export KOPS_STATE_STORE=s3://k8s-com-state-store
export AWS_DEFAULT_REGION=us-east-1
export AWS_ACCESS_KEY_ID=xxx
export AWS_SECRET_ACCESS_KEY=yyy

docker run --rm -it \
    -e AWS_ACCESS_KEY_ID -e AWS_SECRET_ACCESS_KEY -e AWS_DEFAULT_REGION -e KOPS_STATE_STORE \
    -v `pwd`/id_rsa.pub:/tmp/id_rsa.pub -v `pwd`/out/:/out/ -v $HOME/.kube/:/root/.kube/ \
    pottava/kops create cluster --target=terraform --ssh-public-key=/tmp/id_rsa.pub $CLUSTER_NAME
```
