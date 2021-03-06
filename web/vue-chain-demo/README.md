# vue-yy-blockchain-game

> 区块链钱包调用Demo

## Build Setup

``` bash
# install dependencies
$ npm install

# serve with hot reload at localhost:3000
$ npm run dev

# build for production and launch server
$ npm run build
$ npm start

# generate static project
$ npm run generate
```

For detailed explanation on how things work, checkout [Nuxt.js docs](https://nuxtjs.org).


## nuxt项目在服务器上布署

### 布署步骤

1. 第一步，打包：执行`npm run build`，`nuxt`会自动打包
2. 第二步，选择要部署的文件：
	* 方法一：拷贝如下目录到服务器要部署的目录：`.nuxt`、`package.json`、`nuxt.config.js` 文件(如果你部署一些`proxy`，则需要上传这个文件，个人建议把它传上去)
	* 方法二：目录下`Git`克隆下你的项目，然后执行`npm run build`
3. 第三步：后台启动式实例：`npm run start &`
4. 第三步：进程守护式启动： `nohup npm run start  >nohup.out &`
5. 查看日志：`tailf nohup.out`
6. 杀死已启动的守护进程（执行两次）：`kill -9 $(ps -ef|grep -v grep|grep nuxt|awk '{print $2}')`

### 查看启动实例

`ps -ef|grep nuxt`

### 杀死指定实例26736，是通过查看启动实例找到的id

`kill -9 26736`

### 后台启动实例

`npm run start &`

### 进程守方法二：

使用`pm2`启动你的`nuxt.js`。如：`pm2 start npm --name "demo" -- run start`

## pm2常用命令

``` bash
$ npm install pm2 -g      # 安装
$ pm2 start app.js        # 启动
$ pm2 list                # 查看启动列表

$ pm2 stop     <app_name|id|'all'|json_conf>    # 停止某个进程
$ pm2 restart  <app_name|id|'all'|json_conf>    # 重新启动某个进程
$ pm2 delete   <app_name|id|'all'|json_conf>    # 删除某个进程

$ pm2 monit               # 监控日志
$ pm2 reload all          # 重新加载所有

$ pm2 logs
$ pm2 logs APP-NAME       # Display APP-NAME logs 
$ pm2 logs --json         # JSON output 
$ pm2 logs --format       # Formated output 

$ pm2 flush               # Flush all logs 
$ pm2 reloadLogs          # Reload all logs 
```
