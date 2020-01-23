# How to create resources

## Pod

Create a pod - e.g. nginx:

    kubectl run nginx --image=nginx
    
Generate a manifest:

    kubectl run nginx --image=nginx --dry-run -o yaml > nginx-pod.yaml

## Deployment

Create a deployment:

    kubectl create deployment --image=nginx nginx
    
Generate a manifest:

    kubectl create deployment --image=nginx nginx --dry-run -o yaml > nginx-pod.yaml
   
