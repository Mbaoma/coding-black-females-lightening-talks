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
