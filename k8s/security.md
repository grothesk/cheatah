# Security

## Create Certificates and Keys

Create a key for the CA like this:

    openssl genrsa -out ca.key 2048

Create a Certificate Signing Request like this:

    openssl req -new -key ca.key -subj "/CN=KUBERNETES-CA" -out ca.csr
    
Create a self-signed Certificate for the CA:

    openssl x509 -req -in ca.csr -signkey ca.key -out ca.crt
    
