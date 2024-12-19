# 部署指南

软件以Docker镜像的形式发布，Docker镜像为`ttttmr/wechat2rss`，有`amd64`和`arm64`两个版本，支持Apple Silicon

如果你有服务器/电脑，推荐使用Docker Compose部署，推荐1G内存以上配置

如果你没有服务器，或不熟悉Docker，可以试试云服务

[一键部署到Railway](#railway部署)

[一键部署到Sealos](#sealos部署)

[一键部署到Zeabur](#zeabur部署)

## Docker Compose 部署（推荐）

> [!TIP]
> 一键安装Docker和Docker Compose
> `curl -fsSL "https://get.docker.com" | /bin/sh`

下载`docker-compose.yml`

```shell
wget https://wechat2rss.xlab.app/docker-compose.yml
```

修改配置文件，填写`LIC_EMAIL`、`LIC_CODE`和`RSS_HOST`等配置到环境变量中

```shell
vi docker-compose.yml
```

> [!TIP]
> 完整配置和说明见[参数配置](config)

启动服务

```shell
docker compose up -d
```

部署完成后，继续[登录和使用](guide)

### 升级

```shell
docker compose pull
docker compose up -d
```

### 迁移

复制整个部署的文件夹到新服务器，在文件夹里启动服务

```shell
docker compose up -d
```

## Railway部署

点击一键部署，包含自动升级更新

[![Deploy on Railway](https://railway.app/button.svg)](https://railway.app/template/KIQWgJ?referralCode=t4q678)

配置页填写邮箱和激活码等配置

> [!TIP]
> 完整配置和说明见[参数配置](config)

一段时间部署完成后，rss服务会自动分配一个`xxx.railway.app`的域名，打开就可以使用了

需要在页面中填写配置的`RSS_TOKEN`，否则会提示`token is wrong`

> [!TIP] Railway计费说明
> https://railway.app/pricing

部署完成后，继续[登录和使用](guide)

## Sealos部署

### 注册并登录 Sealos

注册地址 [https://cloud.sealos.run](https://cloud.sealos.run/?uid=Gkr1H6rWou)

可以用任意区域，国内国外都可以，但注意价格不同

### 部署

在主页中找到`应用商店`，搜索`Wechat2RSS`

填写邮箱和激活码等配置后点击部署

部署完成后，继续[登录和使用](guide)

### 计费说明

目前模板配置是0.5核，512M内存，1G存储

测试最低0.2核，加载登录二维码有时会卡，其他应该还好

以目前最便宜的北京A区为例，粗略计算

- 存储+端口基础费用 5/月
- 0.5核=6/月 0.2=2.5/月
- 512M 3/月

网络费用另算，基础开销在11-15元/月

> [!TIP]
> 计费价格可能有变动，以官网费用中心计价为准

## Zeabur部署

> [!TIP] 需要至少开通 Developer Plan，计费说明
> https://zeabur.com/pricing

点击一键部署，包含自动升级更新

[![Deploy on Zeabur](https://zeabur.com/button.svg)](https://zeabur.com/templates/OTAL86?referralCode=ttttmr)

配置页填入邮箱和激活码等配置

> [!TIP]
> 完整配置和说明见[参数配置](config)

一段时间部署完成后，rss服务会自动分配一个`xxx.zeabur.app`的域名，打开就可以使用了

部署完成后，继续[登录和使用](guide)