# Security

## Create Certificates and Keys

Create a key for the CA like this:

    openssl genrsa -out ca.key 2048

Create a Certificate Signing Request like this:

    openssl req -new -key ca.key -subj "/CN=KUBERNETES-CA" -out ca.csr
    
Create a self-signed Certificate for the CA:

    openssl x509 -req -in ca.csr -signkey ca.key -out ca.crt
    
Create a new certificate for ETCD clients:

    openssl x509 -req -in /etc/kubernetes/pki/apiserver-etcd-client.csr -CA /etc/kubernetes/pki/etcd/ca.crt -CAkey /etc/kubernetes/pki/etcd/ca.key -CAcreateserial -out /etc/kubernetes/pki/apiserver-etcd-client.crt
