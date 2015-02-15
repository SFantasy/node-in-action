# 服务器部署

本章将介绍如何在AWS(Amazon Web Service)上部署上文中开发的Node.js的应用。

Node.js在Ubuntu等Linux发行版上大概有这么两种安装方式：

1. （更改源后）使用发行版自带的包管理器，例如Debian系的apt-get，CentOS系的yum等
Clone GitHub上Node.js的源码，编译安装
2. Node.js官方给出了使用包管理方式安装Node.js的比较方便的方法：[Install instruction](https://github.com/joyent/node/wiki/Installing-Node.js-via-package-manager#debian-and-ubuntu-based-linux-distributions)，而我也正是使用这种方式安装的:

```
curl -sL https://deb.nodesource.com/setup | sudo bash -
sudo apt-get install nodejs
```

在顺利安装完Node.js之后可以用Vi编辑一个简单的JavaScript文件测试一下：

```
console.log('Hello Node.js and AWS.');
```

## 部署应用

首先我需要checkout GitHub上的repo:

```
git clone https://github.com/SFantasy/Riki.git
```

安装依赖：`npm install`

由于原来Riki中是使用supervisor启动的，在EC2上还是选择使用PM2来运行。

安装PM2：`sudo npm install -g pm2`

修改原来项目种的package.json中的scripts:

```
pm2 start ./bin/www
```

这样就可以通过npm start来运行我们的项目了，如果使用项目默认的3000端口的话就可以直接运行了。
