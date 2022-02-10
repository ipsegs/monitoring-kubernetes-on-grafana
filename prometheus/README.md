# Prometheus deployment and exposing it through a designated nodeport

n/b volume mounted uses emptyDir. This is persistent when a container dies in a pod but not persistent when the container dies 
contents:
1) prometheus-config.yaml- This file contains the configuration for components and files prometheus will scrape.
2) prometheus-deployment.yaml- This file contains the deployment file for prometheus.
3) prometheus-service.yaml- This file exposes prometheus through the NodePort.
4) kustomization.yaml- This file is used to start the other files.

# Starting the grafana deployment
 To start the whole service use this command:
     kubectl apply -k .     
n/b do not ignore the dot

# To view the deployment, because the namespace used is monitoring, use this command:
     kubectl get all -n monitoring| grep prometheus
