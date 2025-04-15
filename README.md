# Creating a Kubernetes Cluster for a containerised application

## Basic Overview

This project involves creating a Kubernetes cluster and deploying a containerised application

## Steps/Instructions

1. Setup Kubernetes in Docker Desktop

   1. Go to Settings and then tab Kubernetes
   2. Tick "Enable Kubernetes"
   3. Click apply and restart

2. Deploy the Dashboard UI using the command in Windows Powershell

```bash
kubectl apply -f https://raw.githubusercontent.com/kubernetes/dashboard/v2.7.0/aio/deploy/recommended.yaml
```

3. Create a sample user by issuing the command below while having downloaded each configuration file

```bash
kubectl apply -f dashboard-adminuser.yaml
```

4. Create a ClusterRoleBinding by running the following:

```bash
kubectl apply -f cluster_role_binding.yaml
```

5. Now, create a pod

```bash
kubectl apply -f createPod.yaml
```

6. Replicate the pods pasting the command below

```bash
kubectl apply -f createReplicaSet.yaml
```

7. Deploy the set of identical pods

```bash
kubectl apply -f createDeployment.yaml
```

8. Create the service for the application using the command below

```bash
kubectl apply -f calc_service.yaml
```

9. Test if the application is working by going to the local port

```bash
http://localhost:31841/divide?n1=10&n2=1
```
