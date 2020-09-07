# k8syaml
configmap配置字典 提供pods调用

cat configmap.yaml

kind: ConfigMap

apiVersion: v1

metadata:

  name: getcustomer
  
  namespace: getvideo-dev-default
  
  labels:
  
    software: getcustomer
    
    project: getcustomer
    
    app: getcustomer
    
    version: v1
    
data:

  appname: getcustomer
  
  apptype: jar
  
  idc: "default"
  
  env: "dev"
  
  host: "172.16.11.138:apollo.51huihuahua.com"
  
  java_Doption: "-server -Xms1g -Xmx1g -XX:MetaspaceSize=512m -XX:MaxMetaspaceSize=512m -XX:+DisableExplicitGC -XX:+UseG1GC -XX:MaxGCPauseMillis=200 -XX:ParallelGCThreads=8 -XX:ConcGCThreads=8 -XX:InitiatingHeapOccupancyPercent=45 -XX:NewRatio=2 -XX:SurvivorRatio=8 -XX:MaxTenuringThreshold=15 -XX:G1ReservePercent=10 -XX:+HeapDumpOnOutOfMemoryError -XX:HeapDumpPath=/data/getcustomer/logs/ -Dserver.port=8080 -Deureka.instance.homePageUrl=http://getcustomer:8080"
  
  java_option: "--server.port=8080"
