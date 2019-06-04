# samba-alpine
一个简单的超级轻量`Samba ` docker 容器，基于最新的`Alpine Linux`镜像。

默认情况下所有的文件是不可见的，对于用户`smart`密码`abc123456`具有读写权限，具体可以查看`conf/smb.conf`文件。  
如果使用网桥模式存在问题请使用`--net=host`

快速开始

```shell
docker run -d --net host -v /path/to/share/:/shared --name samba smarthomefans/samba-alpine-docker
```

端口映射

```shell
docker run -d -p 135:135/tcp -p 137:137/udp -p 138:138/udp -p 139:139/tcp -p 445:445/tcp -v /path/to/share/:/shared --name samba smarthomefans/samba-alpine-docker
```

使用自定义的配置文件

```shell
docker run -d -p 135:135/tcp -p 137:137/udp -p 138:138/udp -p 139:139/tcp -p 445:445/tcp -v /path/to/configs/:/config -v /path/to/share/:/shared --name samba smarthomefans/samba-alpine-docker
```

自动重启

```shell
docker run -d --restart=always -p 135:135/tcp -p 137:137/udp -p 138:138/udp -p 139:139/tcp -p 445:445/tcp -v /path/to/share/:/shared --name samba smarthomefans/samba-alpine-docker
```