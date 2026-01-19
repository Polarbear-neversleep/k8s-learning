# K8S使用手册
本仓库基于K8S学习教程创建使用手册，含全部代码
链接地址：https://guangzhengli.com/courses/kubernetes

# 准备工作(见教程"准备工作")
1. 安装docker
2. 安装minikube
3. 安装kubectl
4. 创建dockerhub账号

# 注意事项
1. 文档中的dockerhub仓库名称请改成自己的再使用
2. 本仓库无连接dockerhub，一切镜像都在本地并导入minikube镜像库中，与教程有一定出入但不影响学习


```
# 镜像导入minikube
minikube image load <镜像名>
```

# 各章细节补充
1. deployment：滚动更新时可以使用 kubectl get pod --watch 查看Pod变动
2. ingress: 无法拉取ingress-nginx,本地自建镜像
3. job: 无法拉取busybox,本地自建镜像(alpine模拟)

# 概念释义
1. Container 容器：一种沙盒技术。它是基于 Linux 中 Namespace / Cgroups / chroot 等技术结合而成。

2. Pod：K8s创建 管理 部署的最小计算单元

3. Deployment: 用k8s自动化操作来管理pod而非直接管理

4. Service: Service 位于 pod 的前面，负责接收请求并将它们传递给它后面的所有pod。一旦服务中的 Pod 集合发生更改，Endpoints 就会被更新，请求的重定向自然也会导向最新的 pod。

5. Ingress: 公开从集群外部到集群内服务的 HTTP 和 HTTPS 路由(可以简单理解为服务的网关 Gateway，它是所有流量的入口，经过配置的路由规则，将流量重定向到后端的服务。)

6. Namespace: 隔离资源，实现dev 环境给开发使用，test 环境给 QA 使用

7. ConfigMap：将你的配置数据和应用程序代码分开，将非机密性的数据保存到键值对中

8. Secret: 包含少量敏感信息例如密码、令牌或密钥的对象。由于创建 Secret 可以独立于使用它们的 Pod

9. Job：一次性任务，只需运行一次得到计算结果即可

10. Helm: 查找、分享和使用软件构建 Kubernetes 的最优方式。

# 补充释义：
1. Node: 集群中的物理机或虚拟机，是Pod真正运行的地方。

2. PV & PVC: Pod销毁后数据会丢失，为了保存数据（如数据库文件），就需要用到PV（存储资源）和PVC（存储申请）。它们让数据独立于Pod的生命周期而存在。

3. StatefulSet: 对应Deployment（无状态），这是专门管理有状态应用（如Redis、MySQL集群）的控制器。它保证Pod有固定的启动顺序和稳定的网络标识。
