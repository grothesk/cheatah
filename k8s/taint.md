# Taints and Tolerations

## Taints

Create a taint on a node like this:

    kubectl taint nodes my-node app=blue:NoSchedule
