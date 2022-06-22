参考: https://cloud.tencent.com/developer/article/1552277
# 部署es
```
kubectl create -f efk/es-deployement.yaml
kubectl create -f efk/es-service.yaml
```
# 部署kibana
```
kubectl create -f efk/kibana-deployement.yaml
kubectl create -f efk/kibana-service.yaml
```
# 部署filebeat
```
kubectl create -f efk/filebeat-cm.yaml
kubectl create -f efk/filebeat-sa.yaml
kubectl create -f efk/filebeat-deploy.yaml
```
# 配置EFK
访问`nodeip:30002`，设置`management-kibana-indexpatterns`，创建index`filebeat-7.3.1-*`，查询日志