### 1 kubernetes init

```bash
sudo kubeadm init \
--kubernetes-version 1.20.2 \
--image-repository=daocloud.io/daocloud \
--control-plane-endpoint=${VIP} \
--apiserver-advertise-address={localhost}  \
--pod-network-cidr=192.168.0.0/16 \
--upload-certs \
-v=5 | tee kubeadm-init.log
```

### 2 Calico  init 

```bash
kubectl create -f https://docs.projectcalico.org/manifests/tigera-operator.yaml
kubectl create -f https://docs.projectcalico.org/manifests/custom-resources.yaml
```

### 3 ingress-nginx init

```bash
kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/nginx-0.30.0/deploy/static/mandatory.yaml
kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/nginx-0.30.0/deploy/static/provider/baremetal/service-nodeport.yaml
```

