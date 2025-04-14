# Microservice Demo Deployment
Online Boutique is a cloud-first microservices demo application. The application is a web-based e-commerce app where users can browse items, add them to the cart, and purchase them. Deploy this e-commerce store in RH OpenShift.

## Architecture
![image](https://github.com/user-attachments/assets/2a8ddc79-ce80-4773-9fe0-ae46e1ee5a25)

![image](https://github.com/user-attachments/assets/f17f6690-bbf1-4358-8e5c-eda698485b18)

## Quickstart

1. Start an OpenShift Cluster
2. Create a project in the Cluster
3. Create Kubernetes Objects by importing the *kubernetes-manifests.yaml* file

> If the Pods crashes, the reason is probably the UserID of the Deployments. Scale down the Deployment to zero pods and again up to one and check out the *Error Message*. Commonly, you need to adjust the User ID (runAsUser, runAsGroup, fsGroup) with the given ID range in the *Error Message*. Every Namespace in OpenShift has a different User ID and the User ID is higher than in Docker Compose e.g. (1000 vs. 10080000). User IDs of 1000 are not accepted in RH OpenShift!

4. Create a Route on the *frontend* Pod (The *frontend-external* pod is the load-balancer)
- Eventually you need to delete cookies or open route in private browser-window
> The e-commerce store should be reachable now 

## Troubleshooting 
If there occur any problems, it could be helpful to deploy every pod one by one ;-)

