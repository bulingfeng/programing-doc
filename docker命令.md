1、最牛docker命令

```shell
docker -h
```

举例

```shell
docker container ls -h
```

2、容器中筛选

```
docker container ls -f 'status=exited' -q
```

更多选项

```
id (容器的id）
label
name（容器名称）
exited （整数-容器退出状态码，只有在使用-all才有用）
status 容器状态（created,restarting,running,paused,exited,dead）
ancestor ([:],or) 过滤从指定镜像创建的容器
before （容器的名称或id）,过滤在给定id或名称之后创建的容器
isolation (default process hyperv) (windows daemon only)
```

3、进入容器中

```
docker container exec -it 容器id/容器名称  /bin/bash
```

```
ctrl+PQ 不停止容器退出
```

