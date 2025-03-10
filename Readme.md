
# basic of k8s
To run a pod in k8s cluster
#kubectl run nginx --image=nginx --port=80 ---> to run the pod of nginx image (this approch is not widly use	d)


#kubectl get pods  ---> This command will list all the pods
# kubectl get nods --> list down your worker nodes


Services:
	1. LoadBalancer 
	2. NodePort 
	3. ClusterIP
 
#Kubectl describe pods pod_name. ---> this command will describe the pod 


# Objects in k8

Pod: Smallest deployable unit 
Services: Expose your application outside 
    - ClusterIP: Expose your application inside the cluster 
    - NodePort: Expose your application out side the cluster on node port 
    - LoadBalancer: Expose your with the help of the load balancer (ELB)  Cloud loadbalancer
Namespace: Devide your cluster 
ReplicationController: Manage your replicas 
ReplicaSet: Manage your replicas
Deployments: Deployments are used to manage your pods in k8s 
StatefullSets: Stateful Sets are use to deploy a application which are dependent
DaemonSets: DaemonSets are used to ensure that a replica of pod is running on each and every node
Congfigmaps: It stores a variables
Secrets: It stores variables in encoded form
HPA: it scales a pods
Ingress: It is use to distribute traffic amongs the services 


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


to scale your rs and rc 
kubectl scale rs --replicas=10 my-rs
kubectl scale rs --replicas=2 my-rs


Stateless Application        |    Statefull Application
HTTPD, Nginx, tomcat         |    Database, Rabitmq, MangoDB

--------------------------

Deployment                      |    Statefull sets
Randomly Pod Created            |    Sequantially Pod Created 
Randomly Pod Deleted            |    Sequantially Pod Deleted
Random hashes in name           |    Sequantially char in name
All pods can Read/write         |    Master Pod can read/write Other pods read
All pods can create from image  |    Only first others can crate form previous

kubectl get sts --> to get statefull 



NAME=Aditi

echo "$NAME is a it engineer" 
echo "$NAME is also a devops trainer"
echo "$NAME Work in cloudblitz" 
echo "$NAME Lives in India"
echo "Hobby of $NAME is travelling" 


Horizontal pod scheling 

HPA stands for Horizontal pod autoscalar . its a k8s feature that automatically scales the number of pods on deployment based on observed CPU and memory usage

Why we use HPA

Ajust the replica count of deployment 
handle sudden traffic spiks automatically 
Reduce manual invervation 



# To install Metrics Server
kubectl apply -f https://github.com/kubernetes-sigs/metrics-server/releases/latest/download/components.yaml
kubectl get pods
kubectl get pods -n kube-system 
kubectl top pods    

if you will not get any output then you should use the following command of patching 
kubectl patch deployment metrics-server -n kube-system --type='json' -p='[
    {"op": "add", "path": "/spec/template/spec/containers/0/args/-", "value": "--kubelet-insecure-tls"}
]'
kubectl get pods -n kube-system



# Ingress controller installation
kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/main/deploy/static/provider/cloud/deploy.yaml


prefix -- cb --> "cbz.com"
exact  -- cb ---> "cbz.com"


---------------------


# Terraform

Terraform -- IAC (Infrastructure as a code)


