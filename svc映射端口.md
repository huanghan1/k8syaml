cat  svc.yaml

apiVersion: v1
 
kind: Service

metadata:

  labels:
  
    name: getcustomer
    
  namespace: getvideo-dev-default
  
  name: getcustomer
  
spec:

  ports:
  
    - port: 8080 
    
      targetPort: 8080
      
  selector:
  
    app: getcustomer
