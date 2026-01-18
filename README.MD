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
