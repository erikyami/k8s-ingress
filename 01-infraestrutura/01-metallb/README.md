# Configuração metallb

## Criando o namespace:

```
kubectl apply -f 01-namespace.yaml 
```

## Aplicando o metallb

```
kubectl apply -f 02-metallb.yaml
```

## Aplicando o metallb-config

Após a configuração do address-pools, aplicar o arquivo de configuração:

```
kubectl apply -f 03-metallb-config.yaml
```
