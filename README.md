# containerized-kwatch
A containerized kwatch instance : Run it where you kubectl proxy from

# run 

```bash
export OPS_HOME=~/.kwatch
export SSH_URI_TO_THIS_RECIPE_S_GIT=git@github.com:pegasus-io/containerized-kwatch.git
export HTTP_URI_TO_THIS_RECIPE_S_GIT=https://github.com/pegasus-io/containerized-kwatch.git

git clone ${HTTP_URI_TO_THIS_RECIPE_S_GIT} ${OPS_HOME}

cd ${OPS_HOME}

mkdir -p $PWD/kwatch/.kube
cp -fR ~/.kube/* $PWD/kwatch/.kube
mkdir -p $PWD/kwatch/.minikube
cp -fR ~/.minikube/* $PWD/kwatch/.minikube


docker-compose -f docker-compose.kwatch.yml build
docker-compose -f docker-compose.kwatch.yml up
# docker-compose -f docker-compose.kwatch.yml logs -f kwatch
```
