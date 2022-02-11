# Configuration for Kube-state-metric server deployment

The kube-state-metric server provides additional cluster information that the normal metrics-server does not.
while metrics-server shows statistics about resource utilization of objects in the kubernetes cluster, Kube-state-metrics listen to the kubernetes API and generates metrics about available kubernetes objects 

#To check the kube-state-metric server:

    kubectl get all -n kube-system | grep kube-state-metric
   or
    kubectl get all -n kube-system # to view it in the kube-system namespace
