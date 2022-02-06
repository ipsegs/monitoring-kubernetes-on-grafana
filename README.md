# Integrating prometheus metrics into grafana and using it to monitor my Kubernetes cluster.

 n/b emptyDir is used as the kubernetes volume.

emptyDir is persistent when a container dies in a pod and it's being restarted but when a pod dies, it is non-persistent.

This project is simple and straightforward.
we created five object files:
1) grafana-prometheus.yaml
2) prometheus-service.yaml
3) grafana.yaml
4) prometheus-config.yaml
5) kustomization.yaml

then we used this command to start the pod:

kubectl apply -k .

