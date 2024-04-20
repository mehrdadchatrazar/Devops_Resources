# Docker Mirror Registry

### 1. Add mirror registry of your choice

```
sudo bash -c 'cat > /etc/docker/daemon.json <<EOF
{
  "insecure-registries" : ["https://docker.arvancloud.ir"],
  "registry-mirrors": ["https://docker.arvancloud.ir"]
}
EOF'
```

### 2. Apply your actions

```
docker logout
sudo systemctl restart docker
```