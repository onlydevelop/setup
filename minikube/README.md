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

## Install Helm

Install helm as follows:

```bash
$ curl https://baltocdn.com/helm/signing.asc | gpg --dearmor | sudo tee /usr/share/keyrings/helm.gpg > /dev/null
$ sudo apt-get install apt-transport-https --yes
$ echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/helm.gpg] https://baltocdn.com/helm/stable/debian/ all main" | sudo tee /etc/apt/sources.list.d/helm-stable-debian.list
$ sudo apt-get update
$ sudo apt-get install helm
```

Reference: https://helm.sh/docs/intro/install/