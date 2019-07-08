# k8syaml
k8s yaml创建详情
cat deployment.yaml

--- 

apiVersion: extensions/v1beta1 

kind: Deployment

metadata:

  namespace: getvideo-dev-default
  
  name: getcustomer
  
  labels:
  
    name: getcustomer
    
spec:

  replicas: 1
  
  template:
  
    metadata:
    
      labels:
      
        app: getcustomer
        
    spec:
    
      imagePullSecrets:
      
      - name: getvideo
      
      containers:
      
      - name: getcustomer
      
        image: 172.16.0.175:18080/getvideo/getcustomer_master:2019.07.08.14.20.42
        
        ports:
        
        - containerPort: 8080  
        
        envFrom:
        
        - configMapRef:
        
            name: getcustomer
            
        volumeMounts:
        
        - mountPath: /data/getcustomer/logs
        
          name: logs
          
      volumes:
      
      - name: logs
      
        hostPath:
        
          path: /data/logs/getvideo/getcustomer/dev/default
          

