# seaweedfs

Install `weed` command line tool via Homebrew:
```bash
brew install seaweedfs
```

Add SeaweedFS helm repo: 
```bash
helm repo add seaweedfs https://seaweedfs.github.io/seaweedfs/helm
```

Install SeaweedFS via Helm:
```bash
helm upgrade -i seaweedfs seaweedfs/seaweedfs \
  --namespace seaweedfs \
  --create-namespace \
  --file values.yaml
```
