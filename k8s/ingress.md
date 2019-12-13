# Ingress

## Ingress with TLS connections

Create a key:
  openssl genrsa -out tls.key 2048
  
Create a certificate using the key:
  openssl req -new -x509 -key tls.key -out tls.cert -days 360 -subj /CN=my.domain.name.com
  

