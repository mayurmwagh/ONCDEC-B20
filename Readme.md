# Objects in k8

Pod: Smallest deployable unit 
Services: Expose your application outside 
    - ClusterIP: Expose your application inside the cluster 
    - NodePort: Expose your application out side the cluster on node port 
    - LoadBalancer: Expose your with the help of the load balancer (ELB)  Cloud loadbalancer
Namespace: Devide your cluster 


# commands
kubectl apply -f filename  --  this command will create your resources 
for e.g
    kubectl apply -f basic-pod.yaml
