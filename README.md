# Sample kubernetes pod manifests

Imparative pod creation:
------------------------
 $ kubectl run kuard --image=gcr.io/kuar-demo/kuard-amd64:1

check the status:

 $ kubectl get pods

delete the running pod:

 $ kubectl delete deployments/kuard

Aletis-MBP:k8s-pods pavan$ kubectl get po
NAME      READY     STATUS    RESTARTS   AGE
pavan     1/1       Running   0          2h

replace <pod-name> with pavan


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


Copying Files to and from Containers:
-------------------------------------
copy from pod to the local machine

$ kubectl cp <pod-name>:/tmp/container.txt ./container.txt

copy into the pod from local machine

$ kubectl cp $HOME/config.txt <pod-name>:/config.txt


Getting More Info with Logs:
----------------------------

$ kubectl logs <pod-name>


Running Commands in Your Container with exec:
---------------------------------------------
executing the command in the container context

$ kubectl exec <pod-name> date

executing the command in the interactive mode

$ kubectl exec -it <pod-name> ash


Liveness Probe:
--------------


Pod Manifests:
=============

Pod manifests include a couple of key fields and attributes: mainly a metadata section for describing the Pod and its labels, a spec section for describing volumes, and a list of containers that will run in the Pod.

Create:
------
$ kubectl apply -f pavan-pod-health.yml

Delete:
------
$ kubectl delete -f pavan-pod-health.yml


