# Ingress

## Ingress with TLS connections

Create a key:

    openssl genrsa -out tls.key 2048
  

Create a certificate using the key:

    openssl req -new -x509 -key tls.key -out tls.cert -days 360 -subj /CN=my.domain.name.com
  

Create a secret:

    kubectl create secret tls tls-secret --cert=tls.cert --key=tls.key
    
    
Specify an Ingress:

```yaml
    apiVersion: extensions/v1beta1 
    kind: Ingress 
    metadata:
      name: myingress
    spec:
      tls:
      - hosts:
        - my.domain.name.com 
        secretName: tls-secret 
      rules:
      - host: my.domain.name.com
        http:
          paths:
          - path: /
            backend:
              serviceName: my-nodeport
              servicePort: 80
```
