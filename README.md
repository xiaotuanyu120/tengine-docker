# tengine-docker

## 创建基于tengine的docker镜像
### 目的
官方没有给镜像，也没有给Dockerfile。所以才需要自己搞一个

### 环境
- alpine镜像版本, 3.3
- tengine版本，2.2.3
- 给tengine打补丁的宿主机，centos 7.5.1804
- `nginx_tcp_proxy_module`-master分支(20181206)

### 遇到的问题
- alpine镜像无法在build时patch`nginx_tcp_proxy_module`模块成功(所以就在本地patch成功之后，将patch后的tengine打包，再传入alpine镜像中)
- `nginx_tcp_proxy_module`的最新release版本中的`tcp.patch`打补丁报错(所以拉取了最新的master分支-20181206)
