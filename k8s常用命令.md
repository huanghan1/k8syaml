创建k8s secret，访问docker私有仓库 k8s对私有仓库授权

#docker-registry=docker的注册名字

#-n:指定namespace 

kubectl create secret docker-registry xiaoniu -n voice-qyeureka-dev --docker-server=192.168.0.90 --docker-username=admin --docker-password=123456 --docker-email=huanghan@xiaoniu.com

查看授权的私有仓库

kubectl get secret -n ${namespace}


#查看认证详情,对应的namespace

kubectl describe secret -n voice-qyeureka-dev


#查看认证详情

kubectl describe secret 

#删除认证注册的名字

#docker-registry=docker的注册名字

kubectl delete   secret xiaoniu registrykey-01

#删除namespace对应secret

kubectl delete  secret  -n  voice-qyeureka-dev  default-token-g5kbl


#查看k8s容器应用

 kubectl get pods -n getvideo-dev-default getcustomer-5c9f9f4cb8-tn6qr

#进入k8s容器

 kubectl exec -it getcustomer-5c9f9f4cb8-tn6qr -n getvideo-dev-default /bin/bash

#查看 deployment 详细信息

kubectl describe  deployment  -n getvideo-dev-default getcustomer

#查看 server 映射的端口 

kubectl get svc -n getvideo-dev-default getcustomer

kubectl  describe svc -n getvideo-dev-default getcustomer
