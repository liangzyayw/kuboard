## kuboard
kubernetes-web图形化管理界面

## 服务部署
`执行一下yaml文件`
```
## 对外暴露端口
kubectl create -f  metrics-server.yaml

## deployment服务部署
kubectl create -f  kuboard-deployment.yaml
```
## 查看执行结果
`查看pod`
>[root@k8s-master ~]# kubectl get pod -n kube-system 
```
NAME                                 READY   STATUS    RESTARTS   AGE
kuboard-7fbf95d77d-gt7qz             1/1     Running   0          7d20h
kuboard-pv-browser-7tbb8             2/2     Running   754        6d3h            ##这个会一直重启
metrics-server-778d6ccc45-wjvvj      1/1     Running   0          7d20h
```

`查看service`
>[root@k8s-master ~]# kubectl get service -n kube-system 
```
NAME                                           TYPE        CLUSTER-IP      EXTERNAL-IP   PORT(S)                  AGE
kuboard                                        NodePort    10.99.79.50     <none>        80:32567/TCP             7d20h
metrics-server                                 ClusterIP   10.104.44.104   <none>        443/TCP                  7d20h
```
