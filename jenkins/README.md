参考: https://segmentfault.com/a/1190000040469278

# 部署jenkins

```
kubectl create -f jenkins/rbac.yaml
kubectl create -f jenkins/deploy.yaml
kubectl create -f jenkins/service.yaml
```

# 初始化Jenkins

- 打开`nodeip:30001`
- 查询admin密码，`kubectl exec jenkins-0 -- cat /var/jenkins_home/secrets/initialAdminPassword`
- 选择自定义插件，不安装任何插件
- 跳过用户创建，使用默认用户admin
- 配置插件源，打开`http://nodeip:30001/pluginManager/advanced`， Update Site填入https://mirrors.tuna.tsinghua.edu.cn/jenkins/updates/update-center.json
- 安装插件
    - Credentials
    - Git Client
    - Git
    - Pipeline相关
    - Basic Step
    - Stage Step
    - Build Step
- 安装完在页面重启jenkins

# 配置CI
目标: 实现修改account服务后自动部署

