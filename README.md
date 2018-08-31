# root-proxy
Helm chart to create pod to add trailing slash to urls mainly as a fix for traefik trailing slash problem. 

When deployed to kubernets with traefik ingress will redirect all requests which doesn't match any other ingress rule.
Includes 
- nginx with redirect configuration


How to deploy to kubernetes using helm


```
export NAME='root-proxy'

export ISPRESENTE=$(helm list|grep -w $NAME)


if [ -z "$ISPRESENTED" ];then
    helm install . --name $NAME --namespace default -f values.yaml --debug 
else
    helm upgrade $NAME . -f values.yaml --debug 
fi
```

