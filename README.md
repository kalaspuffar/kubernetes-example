# kubernetes-example
A small example of how you could setup a simple kubernetes cluster

First we need some commands to work with your cluster these are a good start to both create, delete and find out information.
```
kubectl create -f <yaml file>
kubectl get [deployment|service|pod] <name>
kubectl describe [deployment|service|pod] <name>
kubectl logs <pod name>
kubectl rolling-update <name> -f <yaml file>
kubectl delete [deployment|service] <name>
```

If you are working with both minikube and google cloud it could be nice to be able to switch between these. You can do this by changing context.
```
kubectl config get-contexts
kubectl config set-context <name>
```

Lastly we have some good commands to init and create a new project. Creating clusters that you can run your instance in with specific amount of nodes. Get the configuration of the server so you know what api versions are supported and lastly remove the cluster after your work.
```
gcloud init
gcloud projects create <project name>
gcloud config set project <project id>
gcloud container clusters create example --scopes "cloud-platform" --num-nodes 2 --zone europe-west1-b
gcloud container get-server-config --zone europe-west1-b
gcloud container clusters delete example --zone europe-west1-b
```