######################
Kubernetes
######################

.. include:: ../links.ref
.. include:: ../tags.ref
.. include:: ../abbrs.ref

============ ==========================
**Abstract** Kubernetes
**Authors**  Walter Fan
**Status**   WIP as draft
**Updated**  |date|
============ ==========================

.. contents::
   :local:


Kubernetes 概述
=======================

Kubernetes 是一个用于自动部署、扩展和管理容器化应用的开源系统。它提供了容器编排功能，使开发者可以高效地管理大规模应用。

Kubernetes 主要由以下核心组件组成：

- **Pod**：最小的部署单元，包含一个或多个容器。
- **Service**：提供持久化的访问入口，暴露 Pod 的服务。
- **Deployment**：管理应用的生命周期，支持滚动更新和回滚。
- **ConfigMap 与 Secret**：用于存储配置数据和敏感信息。
- **Ingress**：提供 HTTP/HTTPS 访问控制，管理外部流量。
- **Namespace**：用于逻辑分隔不同环境的资源。

Node
---------------------------
节点，可以是一台云主机，一台树莓派，一部电脑。上面运行了很多 Pod

Pod
---------------------------
一个基本的业务单元, 类似于一个豌豆夹, 可以象放豌豆那边放置镜像。
  一般 instance 和 replica 其实都是指 pod 的实例

Deployment
---------------------------
部署。集群会根据这个资源的定义拉取其中指定的镜像，并创建对应的 Pod，为 Pod 赋予相应的 label 以及其它元数据  
  定义 pod 和容器的 yaml 配置, 定义了要部署多少个 pod 副本等事项

Service
---------------------------
服务。用于定义由哪一些具备对应 label 的 Pod 来承载这个 Service。同时也定义了这个服务会对外提供哪些端口

Ingress
---------------------------
用于定义域名与 Service 的关系。外面的请求进来，集群的 Ingress Controller(nginx) 根据请求的域名对应的 Ingress 资源取得所指向的 Service，再通过 Service 定义的 label 筛选出对应的 Pod


Kubernetes 部署 Nginx 示例
====================================

下面是一个完整的 Nginx 部署示例，包括 Deployment、Service 和 Ingress 配置。

.. code-block:: yaml

   apiVersion: apps/v1
   kind: Deployment
   metadata:
     name: nginx-deployment
     labels:
       app: nginx
   spec:
     replicas: 3
     selector:
       matchLabels:
         app: nginx
     template:
       metadata:
         labels:
           app: nginx
       spec:
         containers:
         - name: nginx
           image: nginx:latest
           ports:
           - containerPort: 80

.. code-block:: yaml

   apiVersion: v1
   kind: Service
   metadata:
     name: nginx-service
   spec:
     selector:
       app: nginx
     ports:
     - protocol: TCP
       port: 80
       targetPort: 80
     type: ClusterIP

.. code-block:: yaml

   apiVersion: networking.k8s.io/v1
   kind: Ingress
   metadata:
     name: nginx-ingress
   spec:
     rules:
     - host: nginx.example.com
       http:
         paths:
         - path: /
           pathType: Prefix
           backend:
             service:
               name: nginx-service
               port:
                 number: 80


应用部署流程
====================================

1. **创建 Deployment**：
   - 运行 `kubectl apply -f deployment.yaml` 以部署 Nginx。
   
2. **创建 Service**：
   - 运行 `kubectl apply -f service.yaml` 以暴露 Nginx。
   
3. **创建 Ingress** (如果集群已配置 Ingress Controller)：
   - 运行 `kubectl apply -f ingress.yaml`。
   
4. **验证部署**：
   - 运行 `kubectl get pods` 查看 Pod 运行情况。
   - 运行 `kubectl get services` 查看 Service 信息。
   - 运行 `kubectl get ingress` 查看 Ingress 状态。


FAQ
=======================


## Shortcuts

.. code-block:: shell

   kubectl get nodes
   kubectl config get-contexts
   kubectl apply -f hellonode_pod.yaml
   kubectl get pods
   kubectl describe pod hello-node
   kubectl apply -f hellonode_svc.yaml
   kubectl get svc
   kubectl delete pod hello-node
   kubectl delete svc hello-node-svc

## How to create a pod from image
* refer to https://github.com/cloudnativedevops/demo/tree/main/hello

.. code-block:: shell

   # build and push image
   docker image build -t hellogo .
   docker image tag hellogo walterfan/hellogo
   docker login
   docker image push walterfan/hellogo
   # run a pod for the image
   kubectl run demo --image=walterfan/hellogo --port=9999 --labels app=demo
   kubectl port-forward pod/demo 9999:8888
   curl -v http://localhost:9999/
   kubectl delete pod demo

## How to get deployments

.. code-block:: shell

   kubectl get deployments --all-namespaces

## 如何查看所有 namespace 中的所有 Services?

要查看Kubernetes集群中所有命名空间（namespaces）里的所有服务（Services），你可以使用``kubectl``命令行工具。以下是具体的步骤和命令：

1. **查看所有命名空间中的Services**：
   使用``kubectl``命令的``--all-namespaces``选项来列出所有命名空间中的Services。命令如下：
   .. code-block:: shell

      kubectl get services --all-namespaces

   这个命令会返回集群中所有命名空间的Services列表。

2. **使用更详细的输出**：
   如果你想获取更详细的信息，比如每个Service的状态和类型，可以使用``-o wide``选项：
   .. code-block:: shell

      kubectl get services --all-namespaces -o wide

3. **过滤特定命名空间的Services**：
   如果你只想查看特定命名空间中的Services，可以省略``--all-namespaces``选项，并指定命名空间：
   .. code-block:: shell

      kubectl get services -n <namespace>

   其中``<namespace>``是你想要查看的命名空间名称。

4. **使用标签过滤**：
   如果你想要基于标签过滤Services，可以使用``-l``选项：
   .. code-block:: shell

      kubectl get services --all-namespaces -l <label-selector>

   其中``<label-selector>``是用于匹配的标签选择器。

5. **查看Services的详细信息**：
   要获取特定Service的详细信息，可以使用``describe``命令：
   .. code-block:: shell

      kubectl describe services --all-namespaces

这些命令将帮助你查看Kubernetes集群中所有命名空间中的所有服务。记得在使用这些命令之前，确保你的``kubectl``配置正确，并且你有足够的权限来访问集群。

## How to get pods info

在Kubernetes（k8s）集群上查看运行的服务通常涉及几个步骤，这里提供一些基本的命令和方法：

1. **查看所有Pods**：
   Pods是Kubernetes中运行应用的最小单元。可以通过以下命令查看所有Pods的状态：
   .. code-block:: shell

      kubectl get pods

   或者，如果你想查看特定命名空间下的Pods，可以使用：
   .. code-block:: shell

      kubectl get pods -n <namespace>

2. **查看所有Deployments**：
   Deployments负责Pods的声明式更新。可以通过以下命令查看所有Deployments：
   .. code-block:: shell

      kubectl get deployments

   同样，你可以指定命名空间：
   .. code-block:: shell

      kubectl get deployments -n <namespace>

3. **查看所有Services**：
   Services定义了访问应用的方式。可以通过以下命令查看所有Services：
   .. code-block:: shell

      kubectl get services

   指定命名空间：
   .. code-block:: shell

      kubectl get services -n <namespace>

4. **查看所有Ingress**：
   如果你使用了Ingress来管理外部访问，可以通过以下命令查看：
   .. code-block:: shell

      kubectl get ingress

   指定命名空间：
   .. code-block:: shell

      kubectl get ingress -n <namespace>

5. **查看特定资源的详细信息**：
   使用``describe``命令可以查看特定资源的详细信息，例如：
   .. code-block:: shell

      kubectl describe pod <pod-name>
      kubectl describe deployment <deployment-name>
      kubectl describe service <service-name>
      kubectl describe ingress <ingress-name>

6. **查看事件**：
   查看集群中发生的事件，这有助于诊断问题：
   .. code-block:: shell

      kubectl get events

7. **使用Dashboard**：
   Kubernetes Dashboard是一个基于Web的用户界面，用于管理集群资源。你可以通过以下命令启动Dashboard：
   .. code-block:: shell

      kubectl dashboard

   然后，在浏览器中访问 `http://localhost:8001/api/v1/namespaces/kubernetes-dashboard/services/https:kubernetes-dashboard:/proxy/`。

8. **使用命令行工具（kubectl）**：
   如果你安装了kubectl，并且配置了正确的kubeconfig文件，你可以直接在命令行中使用上述命令。

确保在使用这些命令之前，你已经安装了kubectl，并且你的kubeconfig配置正确，这样你才能与Kubernetes集群进行通信。如果你在集群上没有足够的权限，某些命令可能会失败。

## How to get nodes info

.. code-block:: shell

   # on ubuntu
   sudo snap install kubectl --classic
   sudo kubectl get nodes

## When and How to Use Kubectl Proxy to Access the Kubernetes API
https://loft.sh/blog/when-and-how-to-use-kubectl-proxy

## How to install kubectl from mirror site

.. code-block:: shell

   sudo apt-get update && sudo apt-get install -y apt-transport-https
   curl -fsSL https://mirrors.aliyun.com/kubernetes-new/core/stable/v1.28/deb/Release.key |
   sudo gpg --dearmor -o /etc/apt/keyrings/kubernetes-apt-keyring.gpg
   echo "deb [signed-by=/etc/apt/keyrings/kubernetes-apt-keyring.gpg] https://mirrors.aliyun.com/kubernetes-new/core/stable/v1.28/deb/ /" | sudo tee /etc/apt/sources.list.d/kubernetes.list
   sudo apt-get update && sudo apt-get install -y kubelet kubeadm kubectl