# Weka CSI Plugin

This scenario will guide you with the basics needed to deploy and use a Weka CSI Plugin in Kubernetes environment.

## Overview

The [Container Storage Interface](https://github.com/container-storage-interface/spec/blob/master/spec.md) \(CSI\) is a standard for exposing arbitrary block and file storage systems to containerized wo
rkloads on Container Orchestration Systems \(COs\) like Kubernetes.

The Weka CSI Plugin provides the creation and configuration of persistent storage external to Kubernetes. CSI replaces plugins developed earlier in the Kubernetes evolution. It replaces the `hostPath` m
ethod to expose WekaFS mounts as Kubernetes volumes.

### Interoperability

* CSI protocol: 1.0-1.2
* Kubernetes: 1.18
* OS \(of Kubernetes worker nodes\): ubuntu 16.04, 18.04
* WekaFS: 3.8 and up

**Note:** For additional Kubernetes/OS versions support contact the Weka support team

### Prerequisites

* Privileged mode must be allowed on the Kubernetes cluster
* The following Kubernetes feature gates must be enabled: DevicePlugins, CSINodeInfo, CSIDriverRegistry, ExpandCSIVolumes \(if not changed, they should be enabled by default\)
* A Weka cluster is installed and accessible from the Kubernetes worker nodes
* The Weka client is installed on the Kubernetes worker nodes
  * It is recommended to use a [Weka client which is part of the cluster](https://docs.weka.io/install/bare-metal/adding-clients-bare-metal#adding-clients-which-are-always-part-of-the-cluster) rather than a [stateless
 client](https://docs.weka.io/install/bare-metal/adding-clients-bare-metal#adding-stateless-clients)
  * If the Kubernetes nodes are part of the Weka cluster \(converged mode on the Weka servers\), make sure the Weka processes come up before `kubelet`
* Filesystems are pre-configured on the Weka system

### Capabilities

#### Supported capabilities

* Static and dynamic volumes provisioning
* Mounting a volume as a WekaFS filesystem directory
* All volume access modes are supported: ReadWriteMany, ReadWriteOnce, and ReadOnlyMany
* Volume expansion

