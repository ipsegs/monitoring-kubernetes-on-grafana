# Starting the namespace and configuring the prometheus clusters.
I added all global clusterRole and clusterRoleBinding configuration into a file since they are not environment or namespace-specific.
Then added the "monitoring namespace" which is where our grafana and prometheus deployment and service will reside.

#To start the process:

   kubectl apply -k .
n/b do not ignore the dot(.)

#To view the namespace:

   kubectl get ns
you should find monitoring as part of the namespaces.

#To view the clusterRole and clusterRoleBinding:

   kubectl get clusterRole
 use
   kubectl get clusterrolebinding to view clusterrolebinding

you should find all clusterRoles and clusterRoleBindings including prometheus and kube-state-metrics.


#To view the metrics kube-state-metrics server would capture:
run
    kubectl proxy
then
    check localhost:8001

