# Cluster

## Update a Cluster

Upgrade the master node - e.g. like this:

    apt-get upgrade -y kubeadm=1.12.0-00
    kubeadm upgrade apply v1.12.0
    apt-get upgrade -y kubelet=1.12.0-00
    systemctl restart kubelet

For each node do the following steps:

1. Drain the node:

        kubectl drain node-name
    
    
2. Upgrade the node:

        apt-get upgrade -y kubeadm=1.12.0-00
        apt-get upgrade -y kubelet=1.12.0-00
        kubeadm upgrade node config --kubelet-version v1.12.0
        systemctl restart kubelet
 
