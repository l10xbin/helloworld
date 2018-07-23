# Hello world project for docker/k8s/istio testing


This project will be built into docker image and do auto deployment,rollback usage

### Build the Docker image
```
$ git clone https://github.com/l10xbin/helloworld.git
$ docker build -t l10xbin/my-python-app .
```

### Download ready image
```
docker pull l10xbin/my-python-app
```

### Run the container

```
docker run -d -p 8080:8080 --name 'running-python-app' l10xbin/my-python-app
```

Now visit http://localhost:8080


### Verify the running container
Verify by checking the container ip and hostname (ID):
```
$ docker inspect -f '{{range .NetworkSettings.Networks}}{{.IPAddress}}{{end}}' my-container
172.17.0.2
$ docker inspect -f '{{ .Config.Hostname }}' my-container

```