It is first required to define a storage class to use the Weka CSI Plugin.

#### Storage Class Example

`/root/examples/csi-wekafs/examples/dynamic/storageclass-wekafs-dir.yaml`{{open}}

#### **Storage Class Parameters**

| **Parameter** | Description | Limitation |
| :--- | :--- | :--- |
| `filesystemName` | The name of the Weka filesystem to create directories in as Kubernetes volumes | The filesystem should exist in the Weka cluster |

Apply the StorageClass and check it has been created successfully:

`kubectl apply -f /root/csi-wekafs/examples/dynamic/storageclass-wekafs-dir.yaml`{{execute}}

Check the storageclass resource has been created:
`kubectl get sc`{{execute}}

It is possible to define multiple storage classes with different filesystems.
