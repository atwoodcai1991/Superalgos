# SUPERALGOS 发出和接收信号

![image](https://user-images.githubusercontent.com/93773753/184357506-230ef79a-cf45-40f9-a1f8-3b83ace321e1.png)


目录：

- 准备工作
- 设置您的[用户配置文件](#set-up-your-user-profile)
- 设置 Superalgos [P2P 环境](#note)
- 设置用于[发送](#outgoing-signals)信号的工作区
- 设置用于[接收](#incoming-signals)信号的工作区
- [故障排除](#troubleshooting-errors)

---

## 准备工作

本 Readme 介绍了 Superalgos 的设置，以便能够从 Superalgos P2P 网络发送或接收*信号*。

假设您已经熟悉 Superalgos。但如果您对此还不太了解，请按照主 README 文件中针对开发者和贡献者的说明进行操作。

您可以从关于安装的视频 https://youtu.be/Q4HVdfNdHbk 或如何创建用户配置文件的视频 https://youtu.be/Sa5B-bwg81A 获取帮助。

无论您想成为*发送者*还是*接收者*，都需要记住几个概念：

- **用户配置文件**对于在 P2P 网络中识别用户来说是必不可少的（例如，发送者可以决定只向特定用户发送信号。接收者可以确保信号是由特定用户发送的，而不是其他人）

- **P2P 网络**对于*发送者*是必需的，但对于*接收者*不是！

- 运行中的**服务器**对于*发送者*是必需的，但对于*接收者*不是！


## 设置您的用户配置文件

![image](https://user-images.githubusercontent.com/38046064/183973288-81b2ccd3-f36e-41b2-92e3-6a0f3c683d9e.png)


*发送者*的用户配置文件设置与接收者的设置略有不同。

#### 对于接收者

设置您的用户配置文件，添加这些节点：

- User Apps > Server Apps > Task Server
- User Apps > Server Apps > Social Trading Server
- User Bots > Social Trading Bots > Social Trading Bot > Available Signals


#### 对于发送者

除了上述所有内容外，还需要：

- User Bots > Social Trading Bots > Social Trading Bot > Available Signals > Trading System Signals > Trading Strategy Signals
- User Bots > Social Trading Bots > Social Trading Bot > Available Storage
- User Storage > Github Storage > Github Storage Container

在您的用户配置文件中的 P2P Network 节点下：
- 添加 Network Services > Trading Signals
- 将 P2P Network Reference 引用到所选网络（用于公共信号的主网或测试网，或您自己的许可 P2P 网络）

注意：在您配置文件中的 Social Trading Bot 节点下，您必须：
- 将 Available Storage Reference 引用到所选的 Github Storage Container
- 编辑/检查 Trading Strategy Signals。在这里您设置要发送哪些信号。更多详细信息可以在"[发出信号](#outgoing-signals)"部分找到


### Github Storage Container

为了能够发送信号，*发送者*必须有一个存储容器。在当前开发中，Superalgos 使用 Github 仓库来托管文件，不用担心它们是加密的 :)

在 Github Storage Container 下：
- 将 codeName 编辑为唯一标识符
- 将 githubUserName 编辑为您的 github 用户账户
- 将 repositoryName 编辑为您将保存交易信号的 github 仓库

您还必须在 Superalgos 文件夹下的 Superalgos/My-Secrets 中添加一个 JSON 文件，创建一个名为 "ApisSecrets.json" 的文件，按以下格式输入以下详细信息。

```js
{
    "secrets": [
        {
            "nodeCodeName": "你在github-storage-container中选择的代码名称",
            "apiToken": "你的github-api-令牌"
        },
        {
            "nodeCodeName": "你在github-storage-container中选择的代码名称-2",
            "apiToken": "你的github-api-令牌"
        }
        ]
}
```


### 签名账户

完成对用户配置文件的更改后，您必须对其进行签名。这是为了确保您就是您，而不是其他人。这是通过配置文件构造器（Governance 项目的一部分）完成的。

- 将您的用户配置文件引用到配置文件构造器
- Profile contructor > Installing signing account
- User Profile > Save Plugin
- **PR 您更新的配置文件**

![image](https://user-images.githubusercontent.com/93773753/184140606-b94435cd-96ec-4ab5-8d22-ed989cab85ef.png)

记得保存您的用户配置文件插件，贡献它并检查它是否已合并到 Governance 仓库。

**重要提示**：您的配置文件被自动合并到 Governance 仓库需要几分钟时间，运行的网络节点再次获取它需要另外 5 分钟。更改配置文件后，等待大约 10 分钟，然后才能期望它能够连接到 Superalgos 网络节点。


## SUPERALGOS P2P 环境

无论您选择通过哪个网络发送信号，或者即使您只想接收信号，您都必须确保在 Environment.js 文件中，将要使用的 P2P 网络必须与用户配置文件 P2P 网络配置同步。

例如，以下是用户 Blaa 托管的许可 P2P 网络的使用示例：

```js
SOCIALTRADING_TARGET_NETWORK_TYPE: 'Permissioned P2P Network',
SOCIALTRADING_TARGET_NETWORK_CODENAME: 'BlaaSignals',
TASK_SERVER_TARGET_NETWORK_TYPE: 'Permissioned P2P Network',
TASK_SERVER_TARGET_NETWORK_CODENAME: 'BlaaSignals',
```

在这种情况下，用户 Blaa（作为*发送者*）必须用这些代码行配置他的网络，而*接收者*也会以相同的方式修改代码，以便能够连接到 Blaa 的许可 P2P 网络。


**目前使用 Testnet 会导致与机器学习项目的干扰，因为他们正在使用 Testnet。这不应该发生，但似乎是一个 bug。**


**注意：** 对于选择的网络需要运行网络节点，如果是许可的 p2p，您需要运行自己的节点。

要运行节点，只需运行以下命令，这将运行您的默认网络节点（默认设置为编号一），
```js
node network
```
如果您想运行任何其他节点，可以使用以下命令，并将数字更改为您的用户配置文件中对应的节点编号。
```js
node network-node-2
```


---
## 发出信号

要能够使用 Superalgos 的内置功能发送信号，您必须将带有特定节点的用户配置文件添加到要使用的交易系统的工作区。您的工作区至少应该如下面的截图所示，包含您的用户配置文件。

![image](https://user-images.githubusercontent.com/93773753/184310271-fd0d171f-a414-4518-af35-2bd806546cd6.png)


### 交易系统

下一步是设置交易系统！

- 将 Trading System Outgoing Signal Reference 引用到 Trading System Signal（在 Social Trading Bot > Available Signals 下）
- 添加您选择的发出信号，您可以添加任意多或少的信号
    - 如果信号基于公式，如果您愿意，可以添加 Signal Context Formula，以进一步编辑要发送的值。
- 将所有发出信号引用到 Trading Strategy Signals 下的正确信号。
    - 例如，交易系统中的市场买入信号转到 Trading Strategy Signals 下的市场买入信号。

![image](https://user-images.githubusercontent.com/93773753/184138630-d169a22a-102d-40fb-ba62-81f2691f0a17.png)


### 交易任务节点

快完成了，在运行交易任务（测试交易任务或生产交易任务）之前，您需要添加几个节点。

- 在任务上添加 Task Server Reference
    - 将 Task Server Reference 引用到用户配置文件中的空闲 Task Server
- 将 Social Trading Bot Reference 添加到 Trading Bot Instance
    - 将 Social Trading Bot Reference 引用到用户配置文件中的正确 Social Trading Bot（将发送您的信号的那个）

![image](https://user-images.githubusercontent.com/93773753/184290130-ecdd07a8-d894-46ee-9252-56a8b05b99a2.png)

---

# 接收信号
设置工作区以从 Superalgos 用户*接收*信号。

要能够使用 Superalgos 的内置功能接收信号，您必须将发送信号的用户配置文件添加到要使用的交易系统的工作区。您的工作区至少应该如下面的截图所示，包含您的用户配置文件。

![image](https://user-images.githubusercontent.com/38046064/184152474-3231b3e1-1cc8-4bc6-bdca-354ae594ff9f.png)


## 用户配置文件
- 添加 User Apps > Server Apps > Task Server
- 添加 User Bots > Social Trading Bots > Social Trading Bot > Available Signals > Incoming Signals

## 接收信号

在这里您添加要在交易系统中使用的信号。
您从发送信号的用户配置文件中引用它们（在 available signals > trading system signals > trading strategy signals 下）

![image](https://user-images.githubusercontent.com/93773753/184138327-1a3fa950-51d6-41ee-bc43-c2c72c75ecb9.png)

信号本身不能用作条件，要将信号用作真/假语句，请在事件的条件中输入以下内容：

```js
if (signals !== undefined && signals.length > 0) {
    true
} else {
    false
}
```

**注意**：您必须添加交易系统信号，否则蜡烛图不会同步。
![image](https://user-images.githubusercontent.com/93773753/184138062-cb032cf4-f01b-4602-9c63-e81a0e7daec4.png)

## 签名账户

- 将您的用户配置文件引用到配置文件构造器
- Profile contructor > Installing signing account
- User Profile > Save Plugin
- **PR 您更新的配置文件**

记得保存您的用户配置文件插件，贡献它并检查它是否已合并到 Governance 仓库。


## 交易任务节点
要将交易信号接收到交易任务中，您需要在运行交易任务（测试交易任务或生产交易任务）之前添加几个节点。

- 在任务上添加 Task Server Reference
    - 将 Task Server Reference 引用到用户配置文件中的空闲 Task Server
- 将 Social Trading Bot Reference 添加到 Trading Bot Instance
    - 将 Social Trading Bot Reference 引用到用户配置文件中的正确 Social Trading Bot（将发送您的信号的那个）

![image](https://user-images.githubusercontent.com/93773753/184290323-d6908658-c318-4e29-b692-f4a08b7078fb.png)

---

# 故障排除错误

### 网络客户端身份

"致命错误。无法运行此任务。网络客户端身份与用户配置文件插件中的任何节点都不匹配。"
当签名账户与 Governance 插件仓库的账户不匹配时会发生此错误。要确保它们相同，请使用 Plugins -> Plugin Project -> Plugin User Profiles 下的"Add specified User Profile"命令在工作区中导入您的用户配置文件。按照 App Setup 中详述的内容向插件添加正确的节点、引用和签名账户。保存插件并将更改推送到 Governance 仓库，等待 10 分钟让它合并并被预测服务器获取。