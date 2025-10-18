# 树莓派安装

树莓派是安装 SuperAlgos 作为生产交易机器人的绝佳平台，但这仅推荐用于最少 UI 使用的实时交易。

## 安装指南

### 要求

1. 按照（主 readme）[https://github.com/Superalgos/Superalgos#small_orange_diamond-installation-for-developers-and-contributors] 中的开发者说明进行操作，除了安装 chrome，您不想让它占用您的树莓派，因为我们无论如何都要使用远程访问！
2. 在树莓派上安装 node 时，通常使用 [nvm](https://github.com/nvm-sh/nvm) 安装更容易。
2. 现在您可以运行 `node platform minMemo noBrowser`，您应该在命令行中看到一些成功的输出。
3. 在连接到您网络的不同机器上打开浏览器，导航到您的树莓派地址和端口 34248 以启动 UI。对我来说，这是 http://192.168.0.132:34248

### 可选要求

- 用于反向代理的 Web 服务器，我将在这里以 (NGINX)[https://www.nginx.com/resources/wiki/start/topics/tutorials/install/] 为例
- 进程管理器，我将在这里以 (PM2)[https://pm2.keymetrics.io/docs/usage/quick-start/] 为例

#### NGINX

如果您不想记住端口号，那么您可以设置反向代理，按照 NGINX 安装指南，您可以编辑文件 */etc/nginx/sites-enabled/default* 并添加您选择的新位置

```conf
server {
    ...
    location /superalgos/ {
        proxy_pass http://localhost:34248/;
    }
}
```
保存文件并重启 nginx `sudo service nginx restart`。

这将允许您导航到 URL 而不是端口。

#### PM2

PM2 是一个基于 node 的进程管理器。使用它意味着您可以在树莓派上永久运行 Superalgos，而不会将其绑定到您的终端窗口。我喜欢的设置方式是在我的主目录中使用 *ecosystem.config.js* 文件，该文件可以用于保存许多不同的进程配置。

```Javascript
module.exports = {
  apps : [{
    name   : "sa", //您选择的进程名称
    script : "platform.js", //启动脚本
    args: "minMemo noBrowser", //树莓派优化操作所需的进程参数
    cwd: "/home/pi/trading/Superalgos/" //执行进程的目录 -- 这是 node_modules 文件夹需要在的地方
  }]
}
```

通过这种设置，您现在可以随意启动和停止进程。警告一下，如果您正在进行代码更改或合并*上游*更新，那么您需要重启应用程序 `pm2 restart sa`。您还可以查看日志 `pm2 logs sa`