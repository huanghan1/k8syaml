
cat namespace.yaml 

apiVersion: v1   # #指定api版本，此值必须在kubectl apiversion中

kind: Namespace  ##指定创建资源的角色/类型

metadata:      # #资源的元数据/属性

   name: voice-qyeureka-dev   ##资源的名字，在同一个namespace中必须唯一
   
   labels:   ##设定资源的标签，详情请见 http://blog.csdn.net/liyingke112/article/details/77482384
   
     name: voice-qyeureka-dev     #自定义注解名字


创建k8s secret，访问docker私有仓库 k8s对私有仓库授权

#docker-registry=docker的注册名字

#-n:指定namespace 

kubectl create secret docker-registry xiaoniu -n voice-qyeureka-dev --docker-server=192.168.0.90 --docker-username=admin --docker-password=123456 --docker-email=huanghan@xiaoniu.com

查看授权的私有仓库

kubectl get secret -n <namespace>


#查看认证详情,对应的namespace

kubectl describe secret -n voice-qyeureka-dev


#查看认证详情

kubectl describe secret 

#删除认证注册的名字

#docker-registry=docker的注册名字

kubectl delete   secret xiaoniu registrykey-01

#删除namespace对应secret

kubectl delete  secret  -n  voice-qyeureka-dev  default-token-g5kbl


