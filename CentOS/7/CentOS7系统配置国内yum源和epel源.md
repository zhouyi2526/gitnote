**首先安装wget`yum install -y wget`**

### 1.首先进入`/etc/yum.repos.d/`目录下，新建一个repo_bak目录，用于保存系统中原来的repo文件

```
[root@localhost~]# cd /etc/yum.repos.d/
[root@localhost yum.repos.d]# mkdir repo_bak
[root@localhost yum.repos.d]# mv *.repo repo_bak/
```

### 2.在CentOS中配置使用网易和阿里的开源镜像

到网易和阿里开源镜像站点下载系统对应版本的repo文件

```linux
[root@localhost yum.repos.d]# wget http://mirrors.aliyun.com/repo/Centos-7.repo

[root@localhost yum.repos.d]# wget http://mirrors.163.com/.help/CentOS7-Base-163.repo

[root@localhost yum.repos.d]# ls
Centos-7.repo  CentOS-Base-163.repo  repo.bak
```

### 3.清除系统yum缓存并生成新的yum缓存

```
[root@localhost yum.repos.d]# ls    	# 列出/etc/yum.repos.d/目录下的文件
Centos-7.repo  CentOS-Base-163.repo  repo.bak

[root@localhost yum.repos.d]# yum clean all		# 清除系统所有的yum缓存

[root@localhost yum.repos.d]# yum makecache		# 生成yum缓存
```

### 4.安装epel源

```
[root@localhost yum.repos.d]# yum install -y epel-release
```

### 5.使用阿里开源镜像提供的epel源

```
[root@localhost yum.repos.d]# wget -O /etc/yum.repos.d/epel-7.repo http://mirrors.aliyun.com/repo/epel-7.repo    # 下载阿里开源镜像的epel源文件
```

### 6.再次清除系统yum缓存，并重新生成新的yum缓存

```
[root@localhost yum.repos.d]# yum clean all		# 清除系统所有的yum缓存

[root@localhost yum.repos.d]# yum makecache		# 生成yum缓存
```

