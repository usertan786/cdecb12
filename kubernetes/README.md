# Kubernetes 
 
- what is Kubernetes ?
- why is Kubernetes ?
- kubernetes architecture 
- kubernetes lifecycle 
- installation of minikube and eks

### List of Objects 
- Pod - smallest entity managing by the Kubernetes.Thin wrapper on container
- Service - expose application in network 
     - ClusterIp - Expose application inside the cluster
     - NodePort - Expose application outside the cluster with the help of Node Ports
     - Load balancer - Expose application outside the cluster using cloud loadbalancers
     - External name
- Volume - mount on pods
     - persistent volume - will last after the pod dies
     - ephemerel volume - will laste till pod running
-  Namespaces - segregate the objects/resources 
- Dployments - manage multiple pods and provides scaling, strategy, and rollback features.
- Replicationcontroller  It ensure that the correct no. pod replicas are running on the ckuster, uses Equality-based selector.
- Replicasets -It ensure that the correct no. of pods replicas are running onthe cluster. Using in, notin, exists operator based selector.
- DaemonSet - To create pod on all nodes / specafic node similar to daemon
- StatefulSet - will provide unique identities to pods even it restart .
- Confiigmaps / Secrets - Use to store the credential
