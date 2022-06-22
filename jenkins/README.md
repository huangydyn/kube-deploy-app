参考: https://segmentfault.com/a/1190000040469278
# 部署jenkins
```
kubectl create -f jenkins/rbac.yaml
kubectl create -f jenkins/deploy.yaml
kubectl create -f jenkins/service.yaml
```

# 配置Jenkins
- 打开`nodeip:30001`
- 查询密钥，`kubectl exec jenkins-xxx -- cat /var/jenkins_home/secrets/initialAdminPassword
  b06be4420bcd4a02ab4968ab02838986`
- 安装插件
- 创建第一个管理员用户

# 配置CI/CD