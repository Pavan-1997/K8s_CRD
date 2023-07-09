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

Created a Custome Object which is based on the CRD created with filename CRD_Test.yml, present in the repo
