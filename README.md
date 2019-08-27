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


### 添加一个站点

在项目的同级目录「默认配置」下新建一个 [laravel/laravel](https://github.com/laravel/laravel) 项目，并命名为 `laravel`。

```
docker-compose-lnmp
laravel
```

创建一个 nginx 配置文件，拷贝 当前项目 `docker-compose-lnmp/nginx/sites/laravel.conf.example` 的文件，删除后缀 `.example`，配置文件最终保持为 `docker-compose-lnmp/nginx/sites/laravel.conf`

#### 重启 nginx 进程

```
docker-compose restart nginx
```



## 启动

```
docker-compose up -d
```


## 常用命令

- 修改软件版本

```
docker-compose build --no-cache mysql
docker-compose restart mysql
```

> 例如上面通过环境配置文件`.env` 修改了数据库的版本，通过 `docker-compose build mysql`重新构建mysql，并使用 `restart` 重启 mysql 进程。
> [参考这个issue](https://github.com/laradock/laradock/issues/1855#issuecomment-433393678)


- 进入容器内部

```
docker-compose exec mysql bash
```
