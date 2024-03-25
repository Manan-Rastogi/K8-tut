minikube start/ delete 
minikube start --driver=docker
minikube dashboard
minikube status


------------- creating a deployment | pod will also be created
kubectl create deployment my-nginx --image=nginx:latest

kubectl get deployments

kubectl get pods


----------- now to use this image we need to bind port
 kubectl expose deployment my-nginx --port=80 --type=LoadBalancer

----> after exposing tell minikube about this service
 kubectl get services
 minikube service my-nginx


 ------------------- Delete Deployment
 kubectl delete deployment my-nginx


--------------- Get Details about pods
-> Visit Dashboard
-> kubectl logs pod_name
-> kubectl describe pods



------------------------------------- Your Project on K8
-> Need to create a docker image and host on dockerhub.
-> Follow same procedure for deployment as done with nginx.


------------------------------------- Updating Project
-> Update Code > Create a new image with next version
-> Push to dockerhub
-> Update K8 Deployment  >>>>>>>  kubectl set image deployment your_deployment_name container_name= new_image_name:new_version
----> Get Container name from pods. (Go to dashboard )
-> Previous Container will be running till this new container goes up.
-> minikube service your_service_name


