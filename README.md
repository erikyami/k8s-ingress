# NGINX Ingress Controller

Um *Ingress* expõe rotas HTTP e HTTPS de fora de um cluster Kubernetes para dentro do cluster. O tráfico das rotas é controlado pelas regras definidas a partir de um "**Ingress Resource**"

Para o Ingress Resource funcionar é necessário ter um **Ingress Controller** rodando no cluster. Somente criar um Ingress resource não surtirá efeito na configuração.

Você pode escolher dentre vários vários Ingress Controllers, este projeto trata da instalação do **NGINX Ingress Controller**


## Instalação

Pressume-se que seu cluster Kubernetes já esteja funcionando. O objetivo é adicionar a funcionalidade de um Ingress Controller no ambiente para permitir o tráfico HTTP/HTTPS para dentro do cluster.

Os procedimentos para a instalação de cluster Kubernetes estão em: https://github.com/erikyami/k8s-centos7

Os diretórios estão enumerados por ordem de execução

- 01-infraestrutura
  - 01-metallb
    - 00-documentacao.txt
    - 01-namespace.yaml
    - 02-metallb.yaml
    - 03-metallb-config.yaml
    - README.md
  - 02-ingress-nginx
    - 00-documentacao.txt
    - 01-mandatory.yaml
    - 02-service-ingress.yaml
    - README.md
  - 03-ssl
    - README.md
  - 04-storage
    - nfs.md


## Documentação 
- https://kubernetes.io/docs/concepts/services-networking/ingress/
- https://kubernetes.io/docs/concepts/services-networking/ingress-controllers/
- https://kubernetes.github.io/ingress-nginx/deploy/
- https://metallb.universe.tf/installation/
