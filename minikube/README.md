# Setup minikube

I am doing it for the arm, you can setup for other ARCH's as well.

## Install Docker

First install DOCKER or any of the driver of your choice. To install docker, following has the quick steps.

Reference: https://docs.docker.com/engine/install/ubuntu/

Then, add the docker user to the group.

```bash
$ sudo usermod -aG docker $USER && newgrp docker
```

## Install Minikube

Install minikube as follows.

```bash
$ curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-arm64
$ sudo install minikube-linux-arm64 /usr/local/bin/minikube
$ minikube start
```

Reference: https://minikube.sigs.k8s.io/docs/start/

## Install kubectl

Install kubectl as follows.

```bash
$ curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/arm64/kubectl"
$ sudo install -o root -g root -m 0755 kubectl /usr/local/bin/kubectl
```

Reference: https://kubernetes.io/docs/tasks/tools/install-kubectl-linux/
