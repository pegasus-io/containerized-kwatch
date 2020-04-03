FROM node:13.12.0-stretch

ARG KUBECONFIG=${KUBECONFIG:-'/root/.kube'}
ENV KUBECONFIG=${KUBECONFIG:-'/root/.kube'}
RUN apt-get update -y && apt-get install -y curl git openssh-server openssh-client
RUN git clone https://github.com/kui-shell/plugin-kubectl-boilerplate 
WORKDIR plugin-kubectl-boilerplate
# RUN npm ci
VOLUME /root/.kube/
VOLUME /root/.minikube/
CMD [ "npm", "start" ]
