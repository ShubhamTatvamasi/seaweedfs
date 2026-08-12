# seaweedfs-csi-driver

Add SeaweedFS CSI Driver helm repo:
```bash
helm repo add seaweedfs-csi-driver https://seaweedfs.github.io/seaweedfs-csi-driver/
```

Install SeaweedFS CSI Driver via Helm:
```bash
helm upgrade -i seaweedfs-csi-driver seaweedfs-csi-driver/seaweedfs-csi-driver \
  --namespace seaweedfs-csi-driver \
  --create-namespace \
  --set isDefaultStorageClass=true \
  --set seaweedfsFiler=seaweedfs-filer-client.seaweedfs.svc.cluster.local:8888
```
