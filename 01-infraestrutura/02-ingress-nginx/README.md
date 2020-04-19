# Configuração Ingress Controller

## Aplicando o arquivo 01-mandatory.yaml:

```
kubectl apply -f 01-mandatory.yaml
```

## Aplicando o 02-service-ingress.yaml

Detalhe que foi adicionado o tipo LoadBalance para o service e que o `loadBalacerIP` é um IP do range do MetalLB, configure com um IP conforme sua rede.

```
kubectl apply -f 02-service-ingress.yaml
```
