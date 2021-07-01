These examples are from an introduction talk on using Kubernetes.

## Environment

The demo environment for this talk used 8 VMs, 7 of which ran RKE (https://rancher.com/products/rke/), and one of which ran a Rancher server (https://rancher.com/products/rancher/) which was hosted on a single k3s system (https://rancher.com/products/k3s/), however the examples should usable with other environments.

A private registry was deployed to the environment based on https://hub.docker.com/_/registry, and the sample rails-app image was built and pushed there.

## Examples

#### 1. Rails App Pod
This file describes a single pod instance of the rails-app. To run:

    kubectl apply -f rails-app-pod.yaml
    kubectl describe pod/my-rails-app

 and to expose with a NodePort service

    kubectl expose pod my-rails-app --type=NodePort
    kubectl describe service/my-rails-app


#### 2. Rails App Deployment
This file describes a deployment with two replicas of the rails-app and a NodePort service. To run, remove any objects created by the previous example and then:

    kubectl apply -f rails-app-deployment.yaml


#### 3. Rails App Deployment with Storage
This example expands on the previous one to use the same NFS storage shared between all rails pods for the sqlite db. To run:

    kubectl apply -f rails-app-deployment-with-storage.yaml



## References

* https://kubernetes.io/docs/concepts/workloads/pods/
* https://kubernetes.io/docs/concepts/workloads/controllers/deployment/
* https://kubernetes.io/docs/concepts/services-networking/service/
* https://rancher.com/docs/rancher/v2.5/en/cluster-admin/volumes-and-storage/examples/nfs/
