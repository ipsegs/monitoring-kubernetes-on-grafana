# Integrating prometheus metrics into grafana and using it to monitor my Kubernetes cluster.

 n/b emptyDir is used as the kubernetes volume.

emptyDir is persistent when a container dies in a pod and it's being restarted but when a pod dies, it is non-persistent.

This project is simple and straightforward.
five declaration file is being created:
1) grafana-prometheus.yaml   - a deployment file for both grafana and prometheus
2) prometheus-service.yaml   - a service file for prometheus to expose the pod to a node and uses NodePort
3) grafana-service.yaml      - a service file for grafana to expose the pod to a node and uses NodePort
4) prometheus-config.yaml    - a configMap file for prometheus to inject configuration into prometheus environment
5) kustomization.yaml        - a templating file containing the resources to be started.

instead of starting the declaration file one after the other, kustomization file is used to start them and in the right order

to start the pod using the kustomization file, use this command:

kubectl apply -k .

