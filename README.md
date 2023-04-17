# Microservices with Kubernetes + GCP/GKE

### The microservices used in the project are [here](https://github.com/lucaswilker14/assembly-voter).

Are they:
- Springboot [ Main Application ]
- RabbitMQ   [ AMQP ]
- Postgres   [ Database ]

Assembly-Voter Image on [Dockerhub](https://hub.docker.com/repository/docker/lucaswilker14/assembly-voter/general)

---
## Installation

* [Docker](https://docs.docker.com/get-docker/)
* [Kubectl](https://kubernetes.io/docs/tasks/tools/)
* [Minikube K8S](https://minikube.sigs.k8s.io/docs/start/)

---

## Run Local K8S

### Steps:

1. Create Cluster:
```
minikube start
```

2. Create new namespace:
```
kubectl create -f namaspaces/ --save-config
```
3. Create new Environments Variables:
```
kubectl create -f config-maps/ --save-config
```

4. Create all microservices deployments:
```
kubectl create -f deployments/ --save-config
```

5. Create all microservices service:
```
kubectl create -f services/ --save-config
```

6. Get service api URL
```
minikube service assembly-voter-svc --url -n assembly-voter-ns
```
7. Enjoy (:


### Application on GKE
--
```
http://35.199.102.229:8080/api/v1/assembly-voter
```


