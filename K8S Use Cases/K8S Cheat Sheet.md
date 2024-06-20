#### A. Running App
(+) `kubectl run + <app name> --image=<repository>/<info>:<tag> --port=<port mapping> --labels app=<app name>`: This will only run application in a pod
==> `kubectl run demo --image=dixluwn/myhello_testk8s:v1.0 --port=9999 --labels app=demo`

(+) `kubectl create deployment <name> --image=<repository>/<info>:<tag>`
==> `kubectl create deployment demo --imaeg=dixluwn/myhello_testk8s:v1.0`

(+) `kubectl port-forward <name> <port mapping>`
==> `kubectl port-forward demo 9999:8888`

(+) `kubectl get pods --selector app=<name>`
==> `kubectl get pods --selector app=demo`

![[Pasted image 20240612154246.png | center]]

#### B. Actions regarding Deployments
(+) `kubectl get all`: To get all resources of all namespace
==> `kubectl get deployment`
==> `kubectl get pod`
==> `kubectl get services`
(+) `kubectl describe <namespace>/<node>`: more details for resource
==> `kubectl describe pod/demo`
(+) `kubectl delete all --selector app=demo`: Clear the environment including the `pod`, `deployment` and `replicaset`.
(+) `kubectl create deployment <name> --image=<repository>/<info>:<tag>`
![[Pasted image 20240612153941.png]]


#### C. Actions regrading Pods
(+) `kubectl get pods --selector app=demo`: Get information about pods
(+) `kubecctl delete pdos --selector app=demo` : delete a pod


#### D. Editing 
(+) `kubectl edit deployment [name]`:

#### E. Describe
(+) `kubectl describe pod [pod name]`:
(+) `kubectl logs [pod name]`

#### F. Execute command
(+) `kubectl exec -it [podname] -- <command>`
==> `kubectl exec -it mongo-depl-887485654-l45v5 -- bin/bash`
(+) `kubectl apply -f config-file.yml`