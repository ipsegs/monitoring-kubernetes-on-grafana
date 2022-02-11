# Grafana deployment and exposing it through a designated nodeport

n/b volume mounted uses emptyDir. This is persistent when a container dies in a pod but not persistent when the container dies 

#contents:
1) grafana-datasource-config.yaml- This file contains the configuration for prometheus integrated into grafana.
2) grafana-deployment.yaml- This file contains the deployment file for grafana.
3) grafana-service.yaml- This file exposes the grafana through the NodePort.
4) kustomization.yaml- This file is used to start the other files.

# Starting the grafana deployment
 To start the whole file use this command:
     kubectl apply -k .     
n/b do not ignore the dot.

# To view the deployment, because the namespace used is monitoring, use this command:
     kubectl get all -n monitoring| grep grafana

#To start the service:

1) port-forward the grafana pod 
           kubectl port-forward <grafana-service-ip> port

2) run this command, find the hostIP and connect to the grafana service NodePort:
           kubectl get pod/grafana-deployment-f647cc5bd-642w8 -o yaml -n monitoring
assuming the grafana service NodePort is 32000 and the hostIP is 172.15.4.3
input this in a web browser "172.15.4.3:32000" and you'd find the grafana login page.

3) using minikube:
           minikube service grafana-svc -n monitoring

to login:
username - admin
password - admin

