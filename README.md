# K8s Custom Resource Definition

A Kubernetes resource is an endpoint in the Kubernetes API that stores a collection of API objects of a certain kind. For example, the built-in Pods resource contains a collection of Pod objects.

In Kubernetes, there are many built-in resources available. Some examples of Kubernetes resources include:

- Deployments
- Pod
- Services
- ConfigMap

Custom Resource(CR):
```  
It is an object that extends the Kubernetes API or allows you to introduce your own API into a cluster.

Custom resources can appear and disappear in a running cluster through dynamic registration, and cluster admins can update custom resources independently of the cluster itself.

Once a custom resource is installed, users can create and access its objects using kubectl, just as they do for built-in resources like Pods.
```
Custom Resource Definition(CRD): 
```
It defines the name and structure of your custom resource that you want to add to the cluster.

CRDs allow users to create new types of custom resources without adding another API server. Defining a CRD object creates a new custom resource with a name and schema that you specify.

When you create a new CRD, the Kubernetes API Server creates a new RESTful resource path to serve and handle the storage of your custom resource. This frees you from writing your own API server to handle the custom resource.
```

Created a CRD with filename crd.yml for name : greeting, present in the repo

Created a Custom Object which is based on the CRD created with filename crd_test.yml, present in the repo

---

1. Create a K8s cluster, using Minikube locally

2. Apply  the CRD in the repo to the cluster

```
kubectl apply -f crd.yml
```

3. Apply Custom Object in the repo to the cluster

```
kubectl apply -f crd_test.yml
```



4. Manage your Custom Oject using kubectl (grt is another name for greeting as defined in YAML)

```
kubectl get grt
```
![image](https://github.com/Pavan-1997/K8s_CRD/assets/32020205/ef8054c6-ad76-4bdd-93ed-59f0c7bfef7c)

5. To view the raw YAML data for the Custom Resource

```
kubectl get grt crd_test -o yaml
```
![image](https://github.com/Pavan-1997/K8s_CRD/assets/32020205/78950315-78a9-4612-b260-c0abd1b50723)

6. To delete a CRD

```
kubectl delete -f crd.yml
```
![image](https://github.com/Pavan-1997/K8s_CRD/assets/32020205/9135fe29-8ef1-47a7-9f5d-66de0d430729)

7. Adding additional Printer Columns

Apply  the crd_printer.yml in the repo to the cluster that adds the REPLICAS, VERSION, and Age columns

```
kubectl apply -f crd_printer.yml
```
![image](https://github.com/Pavan-1997/K8s_CRD/assets/32020205/c360fe9c-66ad-4142-96ab-c7103ceee460)

 


