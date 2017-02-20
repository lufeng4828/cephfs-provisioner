# CephFS Volume Provisioner for Kubernetes 1.5+

Using Ceph volume client

* Build cephfs-provisioner and container image

```bash
go build cephfs-provisioner.go
docker build -t youdomain.com/public/cephfs-provisioner:v1 .
```

* Create a Ceph admin secret

```bash
kubectl create -f ceph-secret-admin.yaml
```

* Start CephFS provisioner
first edit cephfs-provisioner-deploy.yaml change monitors in you side!!!

```bash
kubectl create -f cephfs-provisioner-deploy.yaml
```

* Create a CephFS Storage Class

```bash
kubectl create -f cephfs-storage-class.yaml
```

* Create a pvc

```bash
kubectl create -f cephfs-pvc
```

* Create a Deployment using the pvc

```bash
kubectl create -f cephfs-deploy.yaml
```
