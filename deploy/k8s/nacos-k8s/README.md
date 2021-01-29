https://nacos.io/zh-cn/docs/use-nacos-with-kubernetes.html

### 1 nfs init

```bash
kubectl create -f https://raw.githubusercontent.com/nacos-group/nacos-k8s/v1.1.4/deploy/nfs/rbac.yaml
kubectl create -f https://raw.githubusercontent.com/nacos-group/nacos-k8s/v1.1.4/deploy/nfs/deployment.yaml
kubectl create -f https://raw.githubusercontent.com/nacos-group/nacos-k8s/v1.1.4/deploy/nfs/class.yaml
kubectl get pod -l app=nfs-client-provisioner
```

### 2 nacos-mysql init 

```bash
kubectl create -f https://raw.githubusercontent.com/nacos-group/nacos-k8s/v1.1.4/deploy/mysql/mysql-master-nfs.yaml
kubectl create -f https://raw.githubusercontent.com/nacos-group/nacos-k8s/v1.1.4/deploy/mysql/mysql-slave-nfs.yaml
```

### 3 nacos init

```bash
kubectl create -f https://raw.githubusercontent.com/nacos-group/nacos-k8s/v1.1.4/deploy/nacos/nacos-pvc-nfs.yaml
```
