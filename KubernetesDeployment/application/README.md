### Lister

A very simple application that uses client-go to list `pods` and `deployments` from default namespace.

### Build the binary

```
go build
```

### Build the Docker image

```
» docker build -t application:0.1.1 .
```

If you want to get this deployed on your Kubernetes cluster, push this image to a continer registry

```
docker tag application:0.1.1 <container-registry>/application:0.1.1
docker  push <container-registry>/application:0.1.1
```

Once the image is pushed, change the application.yaml to have this new image for value `.spec.template.spec.containers[0].image`.

### Create deployment

```
kubectl create -f application.yaml
```
