# k8s-demo

After editing K8s configuration files we need to add them to create K8s cluster. Import thing to
applying those configurations files is that first we need to apply configMap and secret files because our deployment and service configurations depending on them.
$ kubectl apply -f <file-name.yaml>

After applying them into cluster we could check all the components created on the cluster by
$ kubectl get all

To check spesific element in the cluster we could use
$ kubectl get <name-of-component> | configMap | secret | ...

To get more information about spesific comment we could use 
$ kubectl describe <name-of-instance> | names of the compenents where we defined in configuration files. 

To access application running on Externally we need to reach the ip address of the cluster. Which means NodePort services is accessible on each Worker Node's IP address. Since we're using minikube in our example we have only one machine.
We can get the ip address by
$ minikube ip
Or we could get it by using kubectl
$ kubectl get node -o wide
