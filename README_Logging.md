# 日志记录文档

Superalgos 由几个应用程序组成，日志记录已经统一以帮助调试。

Superalgos 应用程序包括：

- 平台
- 任务
- 网络
- 社交交易
- 仪表板

每个应用程序都有一个专用的日志文件夹。当每个应用程序启动时，它将初始化一个日志记录器工厂，该工厂将日志输出到命令行和一系列带有日期戳的文件中。日志将被放置在您指定的目录或默认目录 `./Platform/My-Log-Files` 中，这个选定的目录将有一个子文件夹集，每个应用程序一个：

```cmd
./Platform/My-Log-Files
  |-- Dashboards
  |   |-- error/%DATE%.log
  |   |-- combined/%DATE%.log
  |-- Network
  |   |-- error/%DATE%.log
  |   |-- combined/%DATE%.log
  |-- Platform
  |   |-- error/%DATE%.log
  |   |-- combined/%DATE%.log
  |-- Tasks
  |   |-- <TASK_ID>
  |       |-- error/%DATE%.log
  |       |-- combined/%DATE%.log
  |-- SocialTrading
      |-- error/%DATE%.log
      |-- combined/%DATE%.log
```

## 使用方法

所有日志记录器使用相同的工厂提供程序，并具有以下可用方法：

- debug
- info
- warn
- error

要在应用程序中记录日志，请注意文件文件夹结构，因为这将决定在哪里找到您的日志。所有日志记录都应使用 `SA.logger.<method>(...)` 调用。这将自动应用日期戳和方法标签，因此您将得到以下示例：

来自平台应用程序代码

```js
SA.logger.info('Superalgos Platform App is Running!')
```

CLI 输出

```log
2023-01-31T16:44:06.513Z | info | SA | Superalgos Platform App is Running!
```

文件输出

```log
2023-01-31T16:44:06.513Z | info | Superalgos Platform App is Running!
```

来自任务服务器代码

```js
SA.logger.info('Superalgos Task Server is Running!')
```

CLI 输出

```log
2023-01-31T16:45:33.371Z | info | TS | Superalgos Task Server is Running!
```

```log
2023-01-31T16:45:33.371Z | info | Superalgos Task Server is Running!
```

## 日志级别

代码库的大部分使用 info 和 error 日志级别。所有文件日志将写入 info、warn 和 error 日志数据。控制台输出默认将写入相同的日志级别。现在有一个参数可以传递给 CLI 或保存到配置文件以覆盖控制台默认值。

### 更改控制台输出详细程度

要为控制台日志指定不同的输出级别，您可以在启动脚本中添加 `logLevel` 参数。唯一的区别是 'debug'，它也将应用于文件输出 - 原因是很可能是开发人员在临时使用它。

以下所有输入都是有效的，只提供 1 个级别，更严重的所有内容都将被记录：

Debug
- logLevel=debug
- logLevel = debug
- logLevel debug
- -logLevel=debug
- -logLevel = debug
- -logLevel debug
- --logLevel=debug
- --logLevel = debug
- --logLevel debug

Info（默认）
- logLevel=info
- logLevel = info
- logLevel info
- -logLevel=info
- -logLevel = info
- -logLevel info
- --logLevel=info
- --logLevel = info
- --logLevel info

Warn
- logLevel=warn
- logLevel = warn
- logLevel warn
- -logLevel=warn
- -logLevel = warn
- -logLevel warn
- --logLevel=warn
- --logLevel = warn
- --logLevel warn

Error
- logLevel=error
- logLevel = error
- logLevel error
- -logLevel=error
- -logLevel = error
- -logLevel error
- --logLevel=error
- --logLevel = error
- --logLevel error