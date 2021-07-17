### Exercise

To deploy a Flask with Kubernetes

## Steps

1) Build and run docker image, then push it to docker registry

```
docker build -f Dockerfile -t hello-flask:latest .

docker run -p 5000:5000 hello-flask\

docker tag <local_image> username/<push_image_name>

docker tag hello-flask hariprasad10/hello-flask

docker push hariprasad10/hello-flask

```

2) Apply deployment.yaml using kubectl, check the pods are running, then get url and run app

```
kubectl apply -f deployment.yaml

kubectl get pods

kubectl get svc

minikube service hello-world-service
```

## Delete pod

```
kubectl delete pod <pod_name>
```

## Secrets in kubectl

```
kubectl create secret generic empty-secret

kubectl get secret empty-secret

kubectl delete secret empty-secret

kubectl get secrets 
```