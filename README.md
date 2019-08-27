## 介绍

精简 [laradock/laradock](https://github.com/laradock/laradock) 项目。

提取 `nginx + mysql + php-fpm + redis`。


## 安装

通过 git 拷贝仓库配置。

```
git clone https://github.com/curder/docker-compose-lnmp.git
```

## 配置


```
cp .env.example .env
```

修改对应的参数。


默认mysql，redis等容器运行时的数据存放在项目的 `data` 目录下。

## 启动

```
docker-compose up -d
```



## 常用命令

- 修改软件版本

```
docker-compose build mysql
docker-compose restart mysql
```

> 例如上面通过环境配置文件`.env` 修改了数据库的版本，通过 `docker-compose build mysql`重新构建mysql，并使用 `restart` 重启 mysql 进程。
> [参考这个issue](https://github.com/laradock/laradock/issues/1855#issuecomment-433393678)


- 进入容器内部

```
docker-compose exec mysql bash
```
