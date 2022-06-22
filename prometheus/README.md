# 部署Prometheus, Grafana

参考: https://www.qikqiak.com/post/kubernetes-monitor-prometheus-grafana/#%E5%AE%89%E8%A3%85grafana

## 部署Prometheus

- 拉代码`https://github.com/huangydyn/kubeapp.git`
- 创建命名空间`kubectl create namespace kube-ops`
- 安装prometheus
  ```
  kubectl create -f prometheus/node-exporter.yaml
  kubectl create -f prometheus/prometheus-cm.yaml
  kubectl create -f prometheus/prometheus-sa.yaml
  kubectl create -f prometheus/prometheus-deploy.yaml
  kubectl create -f prometheus/prometheus-svc.yaml
  ```
    - 访问prometheus `http://nodeip:32222/targets`

## 部署grafana

- 部署
  ```
  kubectl create -f prometheus/grafana.yaml
  ```
- 登录`http://nodeip:32223/login`，用户名密码admin
- 配置数据源`http://prometheus:9090`
- 导入dashboard: 选择import，填写id 1860