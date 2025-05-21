# fastAPI
Learning the main concepts of FastAPI and how to use it to quickly create web APIs that implement best practices by default.

FastAPI is the framework you’ll use to build your API, and Uvicorn is the server that will use the API you build to serve requests.

## Running the app (locally)
```python
$ python3 -m venv venv
$ source venv/bin/activate
$ pip install -r requirements.txt
$ uvicorn main:app --reload
``` 

The ```-reload``` command means that when you update your application code, the server will reload automatically.
## Containerize the app (Docker)
```bash
$ docker build -t lunchbox .
```

## Running the app (Docker)
```bash
$ docker run -p 8000:8000 lunchbox:latest
```

<img width="1060" alt="image" src="https://github.com/Mbaoma/AKS-Demo/assets/49791498/e631356d-1db0-477a-a9eb-07e47df16c6b">

## Push the app to Docker Hub
```bash
$ docker login #URL - https://hub.docker.com/
$ docker tag lunchbox mbaoma/lunchbox:latest #docker tag docker-image-name dockerhub-username/docker-image-name:tag
$ docker push mbaoma/lunchbox:latest
```

## Pull the app from Docker Hub
```bash
$ docker login #URL - https://hub.docker.com/
$ docker pull mbaoma/lunchbox:latest
$ docker run -p 8000:8000  mbaoma/lunchbox:latest #to test
```

## Running the app (Kubernetes Cluster)
- Set up an Ingress controller in Docker Desktop environment on a Mac
```bash
$ kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/controller-v1.1.0/deploy/static/provider/cloud/deploy.yaml
$ kubectl apply -f ingress.yaml
```

- Apply configurations to run in local environment (I am using Docker Desktop on my Mac)
```
$ kubectl apply -f k8s-config-initial
```

<img width="741" alt="image" src="https://github.com/Mbaoma/fastAPI/assets/49791498/a179ab37-de18-435b-96cd-24cf3c5f6f95">

## ArgoCD Deployment 
- [Install](https://argo-cd.readthedocs.io/en/stable/getting_started/) ArgoCD
- Reference [this](https://github.com/Mbaoma/argocd-local-deployments) repo, to view the deployment.
