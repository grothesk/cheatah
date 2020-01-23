# How to create resources

## Pod

Create a pod - e.g. nginx:

    kubectl run nginx --image=nginx

## Deployment

Create a deployment:

    kubectl create deployment --image=nginx nginx
