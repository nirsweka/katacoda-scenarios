The Weka CSI Plugin deployment is performed via a daemon set.

### Download

Download the Weka CSI Plugin from [GitHub](https://github.com/weka/csi-wekafs) to a master node in the Kubernetes cluster.

The clone command has already been ran as part of the training environemnt startup:
`git clone https://github.com/weka/csi-wekafs.git`	

### Installation

From the downloaded location in the Kubernetes master node, run the following command to deploy the Weka CSI Plugin as a DaemonsSet:

`./csi-wekafs/deploy/kubernetes-latest/deploy.sh`{{execute}}

The number of running pods should be the same as the number of Kubernetes worker nodes. This can be inspected by running:

`kubectl get pods -n csi-wekafsplugin`{{execute}}
