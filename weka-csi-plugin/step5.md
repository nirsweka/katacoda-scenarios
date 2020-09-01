### Useful Commands

Here are some useful basic commands to check the status and debug the service:


get all resources
`kubectl get all --all-namespaces`{{execute}}

get all pods
`kubectl get pods --all-namespaces -o wide`{{execute}}

get all k8s nodes
`kubectl get nodes`{{execute}}

get storage classes
`$ kubectl get sc`{{execute}}

get persistent volume claims
`$ kubectl get pvc`{{execute}}

get persistent volumes
`$ kubectl get pv`{{execute}}

kubectl describe pod/<pod-name> -n <namespace>
`kubectl describe pod/csi-wekafsplugin-dvdh2 -n csi-wekafsplugin`{{execute}}

get logs from a pod
`kubectl logs <pod name> <container name>`

get logs from the weka csi plugin
container (-c) can be one of: [node-driver-registrar wekafs liveness-probe csi-provisioner csi-attacher csi-resizer]
`kubectl logs pods/csi-wekafsplugin-<ID> --namespace csi-wekafsplugin -c wekafs`{{execute}}
```
