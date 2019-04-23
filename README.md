# Sample kubernetes pod manifests

Imparative pod creation:
------------------------
 $ kubectl run kuard --image=gcr.io/kuar-demo/kuard-amd64:1

check the status:

 $ kubectl get pods

delete the running pod:
 $ kubectl delete deployments/kuard


Deleting a Pod:
---------------
Delete it by name

$ kubectl delete pods/pavan

$ kubectl delete -f kuard-pod.yaml

Accessing a Pod:
----------------

$ kubectl port-forward kuard 8080:8080

when you run the above command, you can access it via 
http://localhost:8080