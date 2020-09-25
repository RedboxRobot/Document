# EasyMock安装教程

## 1.安装准备

安装环境准备类容包括

MongoDB：

安装教程见文档https://www.cnblogs.com/TM0831/p/10606624.html，可以设置开机启动服务。

Redis：

https://www.runoob.com/redis/redis-install.html 按照教程下载安装之后需要运行命令 redis-server启动redis服务

Node.js: 

安装并配置环境变量，使用命令node --version 检查安装成功的版本号

## 2.安装EasyMock及相关配置

https://github.com/easy-mock/easy-mock/blob/dev/README.zh-CN.md 下载地址

git clone https://github.com/easy-mock/easy-mock.git

1.先删除下载好的easymock的package-lock.json文件，

2.然后运行npm cache clear --force清理node_moudle依赖，

3.执行npm install安装相关依赖

4.安装好之后修改相关配置文件如下：

 "port": 7300,
 **"host": "127.0.0.1",**
 "pageSize": 30,
 "proxy": false,
 **"db": "mongodb://localhost:27017/easymockdb",**
 "unsplashClientId": "",
 "redis": {
  "keyPrefix": "[Easy Mock]",
  **"port": 6379,**
  "host": "localhost",
  "password": "",
  "db": 0
 },

5.执行npm run build编译

6.执行npm run dev打开eastmock 的网页

7.开启守护进程：

在项目目录下使用pm2守护运行：cross-env NODE_ENV=production pm2 start app.js



