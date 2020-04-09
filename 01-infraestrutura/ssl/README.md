# Criar certificado autoassinado para utilizar no Ingress

Documentação: https://kubernetes.github.io/ingress-nginx/user-guide/tls/


## Criando o certificado:
### Criando a chave privada:
```
openssl genpkey -algorithm rsa -pkeyopt rsa_keygen_bits:2048 -out wildcard.example.com.key
```


### Criando uma CSR - "Certificate Signing Request - Requisição para Assinatura de Certificado" com a chave que foi criada:
```
openssl req -new -key wildcard.example.com.key -out wildcard.example.com.csr
```


### Criando um certificado autoassinado:
```
openssl x509 -req -days 365 -signkey wildcard.example.com.key -in wildcard.example.com.csr -out wildcard.example.com.crt
```


## Criando a secret
```
kubectl create secret tls wildcard-tls-secret --key wildcard.example.com.key --cert wildcard.example.com.crt
```

### Verificando a secret criada:
```
[kubeadmin@master ssl]$ kubectl get secrets 
NAME                   TYPE                                  DATA   AGE
default-token-qnvhf    kubernetes.io/service-account-token   3      45h
wildcard.example.com   kubernetes.io/tls                     2      3m46s
```
