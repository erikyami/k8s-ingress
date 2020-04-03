## Infraestrutura

Os diretórios estão numerados em ordem de execução.


### MetalLB

No Kubernetes, serviços de tipo "LoadBalancer" aguardam um IP Externo a partir de um *network load-balancer*. Esta funcionalidade é disponibilizada nos *Cloud Providers*.

O MetalLB faz este trabalho de *network load-balancer* em um ambiente bare-metal, ou seja, que não esteja rodando na nuvem e sim na infraestrutura local da organização.

### Ingress

Arquivos de configuração para a instalação do NGINX Ingress Controller no kubernetes

### SSL

Criação de um certificado SSL autoassinado e criação de secret para utilizar comunicações seguras através do protocolo HTTPS

