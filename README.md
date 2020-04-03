# NGINX Ingress Controller

Um *Ingress* expõe rotas HTTP e HTTPS de fora de um cluster Kubernetes para dentro do cluster. O tráfico das rotas é controlado pelas regras definidas a partir de um "**Ingress Resource**"

Para o Ingress Resource funcionar é necessário ter um **Ingress Controller** rodando no cluster. Somente criar um Ingress resource não surtirá efeito na configuração.

Você pode escolher dentre vários vários Ingress Controllers, este projeto trata da instalação do **NGINX Ingress Controller**

## Documentação 
- https://kubernetes.io/docs/concepts/services-networking/ingress/
- https://kubernetes.io/docs/concepts/services-networking/ingress-controllers/
- https://kubernetes.github.io/ingress-nginx/deploy/
- https://metallb.universe.tf/installation/
