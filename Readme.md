# Objects in k8

Pod: Smallest deployable unit 
Services: Expose your application outside 
    - ClusterIP: Expose your application inside the cluster 
    - NodePort: Expose your application out side the cluster on node port 
    - LoadBalancer: Expose your with the help of the load balancer (ELB)  Cloud loadbalancer
Namespace: Devide your cluster 
ReplicationController: Manage your replicas 
ReplicaSet: Manage your replicas


# commands
kubectl apply -f filename  --  this command will create your resources 
for e.g
    kubectl apply -f basic-pod.yaml
kubectl delete -f filename -- this will delete your resources
    kubectl delete -f basic-pod.yaml 
kubectl descibe pod_name -- this will describe your pods 
kubectl get pods -o wide -- this will show wider information of your pods


# commands
kubectl get ns
kubectl get pods  #this command will list the pods which are in default namespace  
kubectl get pods -n dev #this command will show pods of dev namespace



# commands 
kubectl get rc  # this will show the replication controller in your cluster



rc --> v1
        previous generation
        selector
            app: my-app 

rs  --> app/v1 
        advance generation   
        set base selector 
        
        set base oprators
        In, NotIn, Exist


Set { apple, banana, mango, orange }
list [ apple, banana, orange ]


100 pods

app: cbz
app: dyl
app: gremio
env: prod
env: dev
env: release
