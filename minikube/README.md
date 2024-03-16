# Setup minikube

I am doing it for the arm, you can setup for other ARCH's as well.

First install DOCKER or any of the driver of your choice. To install docker, following has the quick steps.

Reference: https://docs.docker.com/engine/install/ubuntu/

Then, add the docker user to the group.
```bash
$ sudo usermod -aG docker $USER && newgrp docker
```

Finally, install minikube.
```bash
$ curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-arm64
$ sudo install minikube-linux-arm64 /usr/local/bin/minikube
$ minikube start
```

Reference: https://minikube.sigs.k8s.io/docs/start/
