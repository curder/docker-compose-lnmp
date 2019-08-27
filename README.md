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



