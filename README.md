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

You can read help document:  
`docker run --rm pottava/kops`

Or you can alias common prefix:

```
alias kops="docker run --rm pottava/kops"
kops create cluster $CLUSTER_NAME --yes
```
