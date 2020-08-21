# manjaro安装docker
### 安装
`$ sudo pacman -S docker`
### 启动 Docker 服务：

`$ sudo systemctl start docker.service`
如果有需要的话还可以把 Docker 添加到启动项， 让 Docker 在每次系统启动时自动运行：

`$ sudo systemctl enable docker.service`
### 将用户添加到 Docker 组中

Docker 默认只能通过 root 权限执行操作， 但通过将用户添加到 docker 用户组可以规避这一点：

`sudo usermod -aG docker zhouyi`

Docker 默认使用的是外国源， 访问速度很慢而且很容易断线， 为此我们可以使用国内的镜像来代替默认的源。

打开或创建 /etc/docker/daemon.json 文件， 将选中的镜像地址添加到 registry-mirrors 数组里面（可同时填入多个镜像）：
```
{
    "registry-mirrors": [
        "https://registry.docker-cn.com"
    ]
}
```
这里的 registry.docker-cn.com 是 Docker 的官方中国镜像， 除此之外还有其他一些第三方镜像可选：

镜像地址

Azure 中国 `https://dockerhub.azk8s.cn`

中科大 `https://docker.mirrors.ustc.edu.cn`

七牛云 `https://reg-mirror.qiniu.com`

网易云 `https://hub-mirror.c.163.com`

腾讯云 `https://mirror.ccs.tencentyun.com`

保存文件之后重启一下 Docker 服务：

`sudo systemctl daemon-reload`
`sudo systemctl restart docker`