# Monitoring a kubernetes cluster using prometheus metrics scraping the cluster and dashboard using grafana.
n/b emptyDir is used as the kubernetes volume.
emptyDir is persistent when a container dies in a pod and it's being restarted but when a pod dies, it is non-persistent.

To create a persistent volume, you'd have to create a persistent volume, a persistent volume claim and for dynamic provisioning, you should create a storage class.
That's another project i may likely work on later.

#This project consists of 4 folders: 
1) cluster-role-and-namespace 
2) kube-state-metrics
3) prometheus
4) grafana.

#Start the process in the order of arrangement.
there's a kustomization file in each folder to start each folder content in the right order.

To start each folder, simple instructions are provided in the readme file of each folders.
