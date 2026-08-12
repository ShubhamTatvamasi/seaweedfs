# seaweedfs

Install `weed` command line tool via Homebrew:
```bash
brew install seaweedfs
```

Add SeaweedFS helm repo: 
```bash
helm repo add seaweedfs https://seaweedfs.github.io/seaweedfs/helm
```

Install SeaweedFS via Helm - single node (for testing only):
```bash
helm upgrade -i seaweedfs seaweedfs/seaweedfs \
  --namespace seaweedfs \
  --create-namespace \
  --set master.replicas=1 \
  --set filer.replicas=1 \
  --set volume.replicas=1 \
  --set master.data.type=hostPath \
  --set "volume.dataDirs[0].name=data1" \
  --set "volume.dataDirs[0].type=hostPath" \
  --set "volume.dataDirs[0].hostPathPrefix=/data/seaweedfs" \
  --set "volume.dataDirs[0].maxVolumes=0" \
  --set filer.data.type=emptyDir \
  --set admin.enabled=true \
  --set admin.secret.adminUser=admin \
  --set admin.secret.adminPassword=admin

```

access admin dashboard via port-forwarding:
```bash
kubectl port-forward -n seaweedfs svc/seaweedfs-admin 23646:23646
```

http://localhost:23646

---

Install SeaweedFS via Helm:
```bash
helm upgrade -i seaweedfs seaweedfs/seaweedfs \
  --version 4.41.0 \
  --namespace seaweedfs \
  --create-namespace \
  --file values.yaml
```
