Using a similar storage class to the above, it is possible to define a persistent volume claim \(PVC\) for the pods.

#### Persistent Volume Claim Example

`csi-wekafs/examples/dynamic/pvc-wekafs-dir.yaml`{{open}}

#### Persistent Volume Claim **Parameters**

| **Parameter** | Description | Limitation |
| :--- | :--- | :--- |
| `spec.accessModes` | The volume access mode | `ReadWriteMany`, `ReadWriteOnce`, or `ReadOnlyMany` |
| `spec.storageClassName` | The storage class to use to create the PVC | Must be an existing storage class |
| `spec.resources.requests.storage` | A desired capacity for the volume | The capacity quota is not enforced but is stored on the filesystem directory extended attributed for future use |

Apply the PersistentVolumeClaim and check it has been created successfully:

`kubectl apply -f /root/csi-wekafs/examples/dynamic/pvc-wekafs-dir.yaml`{{execute}}

Check the pvc resource has been created:
`kubectl get pvc`{{execute}}
