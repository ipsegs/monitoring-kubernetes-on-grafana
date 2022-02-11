# Prometheus deployment and exposing it through a designated nodeport

n/b volume mounted uses emptyDir. This is persistent when a container dies in a pod but not persistent when the container dies 

#contents:
1) prometheus-config.yaml- This file contains the configuration for components and files prometheus will scrape.
2) prometheus-deployment.yaml- This file contains the deployment file for prometheus.
3) prometheus-service.yaml- This file exposes prometheus through the NodePort.
4) kustomization.yaml- This file is used to start the other files.

# Starting the prometheus deployment
 To start the whole service use this command:
     kubectl apply -k .     
n/b do not ignore the dot

# To view the deployment, because the namespace used is monitoring, use this command:
     kubectl get all -n monitoring| grep prometheus

#To start the service:

1) port-forward the prometheus pod 
           kubectl port-forward <prometheus-service-ip> port -n monitoring

2) run this command, find the hostIP and connect to the grafana service NodePort:
           kubectl get <grafana-pod-name> -o yaml -n monitoring
assuming the grafana service NodePort is 32000 and the hostIP is 172.15.4.3
input this in a web browser "172.15.4.3:32000" and you'd find the grafana login page.

3) Using minikube:
     minikube service prometheus-service -n monitoring

#To check for scraped metrics on prometheus:

after accessing the prometheus UI through a web browser, click on status and check around each tabs most especially targets for the set metrics. 
