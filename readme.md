## Build + Publish => Deployment => Service Configuration

### Docker basic command to build and run

```
#1
Build: docker build .
Runn: docker run id_of_image
Tagging an image*1: docker build -t khairul100/dotnet5-hw-img .
Run tagged image*2: docker run khairul100/dotnet5-hw-img
               OR docker run -p 3000:3000 khairul100/dotnet5-hw-img
               OR docker run --name dotnet5-hw-con -d -p 8001:80 khairul100/dotnet5-hw-img
Publish image*3: docker push khairul100/dotnet5-hw-img
```

### kubernetes basic command to build and run

```
Pod:
Creating Pod: kubectl apply -f posts.yaml
Get Pods: kubectl get pods
Execute: kubectl exec -t posts
Logs: kubectl logs
Delete Pod: kubectl delete pod posts
Event Log: kubectl describe pod posts

Deployment#2:
Creating Deployment*1: kubectl apply -f dotnet5-hw-dep.yaml 
                   OR  kubectl apply -f .
Rollout & Restart*1.2(when code is updated): kubectl rollout restart deployment deployment_name_here
Get Pods*2: kubectl get pods
Expose with Port*2.1: kubectl expose pod dotnet5-hw-pod --type=NodePort --name dotnet5-hw-svc
Get Deployment*2: kubectl get deployments
Delete Deployment: kubectl delete deployment posts
Event Log: kubectl describe deployment posts
Logs*3: kubectl logs pod_name_here

Create Pod: kubectl create -f dotnet5-hw-pod.yml

Service#3:
Creating Service*1: kubectl apply -f dotnet5-hw-svc.yaml
Get Services*2: kubectl get svc
Event Log*3: kubectl describe svc dotnet5-hw-svc
```

### Skaffold Setup to deploy & publish auto

```
Install from here*1: https://skaffold.dev/docs/install/ OR
Installl Chocolatey then install skaffold using powershell : choco install -y skaffold
Configure skaffold.yaml
Run command 'skaffold dev' from root directory
```

### Docker & kubernetes usefull command

```
docker ps --format= format_here
```
