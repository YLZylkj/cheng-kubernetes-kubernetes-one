# Kubernetes Linux安装
kubectl 版本和集群版本之间的差异必须在一个小版本号内。 例如：v1.23 版本的客户端能与 v1.22、 v1.23 和 v1.24 版本的控制面通信。 用最新兼容版的 kubectl 有助于避免不可预见的问题。
## 在 Linux 系统中安装 kubectl

在 Linux 系统中安装 kubectl 有如下几种方法：
- 用 curl 在 Linux 系统中安装 kubectl
- 用原生包管理工具安装
- 用其他包管理工具安装
### 用 curl 在 Linux 系统中安装 kubectl 

#### 1、用以下命令下载最新发行版：<br>

``
curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"
``

Note:
如需下载某个指定的版本，请用指定版本号替换该命令的这一部分：​ $(curl -L -s https://dl.k8s.io/release/stable.txt)。 ​

例如，要在 Linux 中下载 v1.23.0 版本，
请输入：<br>
`curl -LO https://dl.k8s.io/release/v1.23.0/bin/linux/amd64/kubectl`

### 2、安装 kubectl
`apt install sudo`<br>
`sudo install -o root -g root -m 0755 kubectl /usr/local/bin/kubectl`<br>
即使你没有目标系统的 root 权限，仍然可以将 kubectl 安装到目录 ~/.local/bin 中：<br>
``
chmod +x kubectl
mkdir -p ~/.local/bin
mv ./kubectl ~/.local/bin/kubectl
``
<br>之后将 ~/.local/bin 附加（或前置）到 $PATH

### 4、执行测试，以保障你安装的版本是最新的：
`kubectl version --client`<br>
或者使用如下命令来查看版本的详细信息：
`kubectl version --client --output=yaml`<br>