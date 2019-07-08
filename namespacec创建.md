
cat namespace.yaml 

apiVersion: v1   # #指定api版本，此值必须在kubectl apiversion中

kind: Namespace  ##指定创建资源的角色/类型

metadata:      # #资源的元数据/属性

   name: voice-qyeureka-dev   ##资源的名字，在同一个namespace中必须唯一
   
   labels:   ##设定资源的标签，详情请见 http://blog.csdn.net/liyingke112/article/details/77482384
   
     name: voice-qyeureka-dev     #自定义注解名字
