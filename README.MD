# FastAdmin 开发容器

这是一个用于 FastAdmin 的开发容器，FastAdmin 是一个基于 PHP 的框架。它建立在 PHP-FPM 7.4 之上，并包含内置的 MySQL 服务。这个容器为开发 FastAdmin 应用程序提供了一个便利的环境。

## 先决条件

在使用 FastAdmin 开发容器之前，请确保您的系统上安装了以下软件：

- Docker: [Install Docker](https://docs.docker.com/get-docker/)
- Docker Compose: [Install Docker Compose](https://docs.docker.com/compose/install/)

# 特性
- 基础容器使用php-fpm，支持使用`docker-php-ext-install` 启用安装需要的插件
- 容器内置了：nginx,git,docker，方便开发容器内编译项目
- 也支持在windows/DockerDesktop下启动，完全摆脱windows开发fa的困境
- 容器开发随时可以停止，不占用资源，使用docker compose，内置mysql



## 入门指南


要开始使用 FastAdmin 开发容器，请按照以下步骤操作：


1. 进入项目工程 `cd workspace``
2. 克隆 FastAdminDevContainer 仓库: `git clone https://github.com/liuhuapiaoyuan/fastadmin_devcontainer.git` .devcontainer
3. 使用vscode的devcontainer启动
4. 内置的mysql服务提供如下：
`
MYSQL_ROOT_PASSWORD: root
MYSQL_DATABASE: fastadmin
MYSQL_USER: fastadmin
MYSQL_PASSWORD: root  
` 


## 配置

开发容器附带默认配置设置。如果您需要自定义任何设置，可以修改 docker-compose.yml 文件。


 

## License

This project is licensed under the [MIT License](LICENSE).
