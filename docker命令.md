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

4、docker镜像筛选

```
docker images repository'name
```

举例

```
docker images redis
```

5、查询出来没有标签的镜像

```
docker image ls --filter dangling=true
```

可能是如下问题造成的

```
通常出现这种情况，是因为构建了一个新镜像，然后为该镜像打了一个已经存在的标签。
当此情况出现，Docker 会构建新的镜像，然后发现已经有镜像包含相同的标签，接着
Docker 会移除旧镜像上面的标签，将该标签标在新的镜像之上。
```

异常全部没有标签的镜像

```
docker image prune
```

> docker image prune -a 代表的是额外移除没有被使用的镜像。

6、全能搜索命令

搜索镜像是redis的

```
docker images -f reference="redis"
```

搜索tag为latest镜像

```
docker image ls --f reference="*:latest"
```

7、搜索镜像

```
docker search 镜像名
```

搜索指定官方

```
docker search 镜像名 -f "is-official=true"
```

