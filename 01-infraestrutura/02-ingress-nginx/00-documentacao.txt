

Documentação:

https://kubernetes.github.io/ingress-nginx/deploy/



kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/nginx-0.30.0/deploy/static/mandatory.yaml
kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/nginx-0.30.0/deploy/static/provider/baremetal/service-nodeport.yaml


Verificar instalacao
kubectl get pods --all-namespaces -l app.kubernetes.io/name=ingress-nginx --watch

