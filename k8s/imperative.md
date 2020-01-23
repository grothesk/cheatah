# How to create resources

## Pod

Create a pod - e.g. nginx - like this:

    kubectl run --generator=run-pod/v1 nginx --image=nginx
    
Generate a manifest:

    kubectl run --generator=run-pod/v1 nginx --image=nginx --dry-run -o yaml > nginx-pod.yaml

## Deployment

Create a deployment like this:

    kubectl create deployment --image=nginx nginx
    
Generate a manifest:

    kubectl create deployment --image=nginx nginx --dry-run -o yaml > nginx-pod.yaml
   
## Namespace

Create a namespace like this:

    kubectl create namespace my_namespace
