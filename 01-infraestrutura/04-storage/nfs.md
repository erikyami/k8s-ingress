# Configuração do servidor NFS

Alguns projetos necessitarão de persistência de dados, para isto o cluster Kubernetes deve ter acesso a um filesystem distribuído para armazenar as informações que serão persistidas.

Inicialmente utilizarei o NFS (Network File System) como storage, mas há outras opções como CEPH, GLUSTERFS, entre outros.

## Instalação do NFS no Servidor

Em uma máquina fora do cluster Kubernetes vamos instalar os pacotes necessários para disponibilizar o armazenamento:

```
sudo yum -y install nfs-utils
```

### Criar diretório que será compartilhado

```
sudo mkdir -p /mnt/dados
```


### Configurando arquivo /etc/exports

```
sudo vi /etc/exports

/mnt/dados   192.168.56.*(rw,no_root_squash)
```

Onde:

 - "/mnt/dados":  é o diretório a ser compartilhado na rede 
 - "192.168.56.\*":  é uma expressão para representar a rede
 - "rw": é a forma de compartilhamento (Leitura e Escrita)
 - "no_root_squash": é para o servidor entender que o *root* do cliente terá as mesmas permissões do *root* servidor.


### Configurando a inicialização dos serviços


```
sudo systemctl enable rpcbind
sudo systemctl enable nfs-server
sudo systemctl start rpcbind
sudo systemctl start nfs-server
```

### Exportando os diretórios

Para que a configuração do arquivo /etc/exports surta efeito, temos executar um comando explícito para isto:

```
sudo exportfs -avr
exporting 192.168.56.*:/mnt/dados
```

Os diretórios compartilhados podem ser visualizados através do comando:

```
sudo exportfs -s
/mnt/dados  192.168.56.*(sync,wdelay,hide,no_subtree_check,sec=sys,rw,secure,no_root_squash,no_all_squash)
```

## Instalação do NFS nos Clientes

Para que os nós do cluster Kubernetes sejam capazes de realizar a montagem de um compartilhando NFS, é preciso instalar os pacotes clients do NFS:

Realizar o seguinte comando nos nodes (workers) do Kubernetes:

```
sudo yum -y install nfs-utils
sudo systemctl enable nfs-utils
sudo systemctl start nfs-utils
```
