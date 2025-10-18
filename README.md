# :small_orange_diamond: 使用说明

## 运行客户端和 GUI

### 使用快捷方式

如果您在安装依赖项时运行了 `node setup shortcuts`，那么您应该有一个桌面图标，双击它可以启动 Superalgos 应用程序。终端窗口将显示服务器正在运行，浏览器窗口将打开 GUI。

### 使用命令行

要运行 Superalgos，进入 Superalgos 目录/文件夹并运行此命令：

```sh
node platform
```

选项用法：

```sh
node platform <选项> <项目> <工作区>
```

| 选项 | 描述 |
| --- | --- |
| `minMemo` | 以最小内存占用运行。这对于在 8GB 或更少 RAM 的平台上运行非常重要，比如树莓派。 |
| `noBrowser` | 不在浏览器中打开 GUI。这在没有 UI 的无头服务器上很有用。 |

要在启动时加载特定的工作区，添加您可能需要的任何选项，然后是项目，然后是工作区。例如，要在没有选项的情况下加载 Foundations 项目的 Blank-Template 工作区：

```sh
node platform Foundations Blank-Template
```

客户端将在您的终端上运行，GUI 将在您的默认浏览器中启动。如果 Chrome/Safari 不是您的默认浏览器，复制 URL，关闭浏览器，打开 Chrome/Safari，并粘贴 URL。请耐心等待...GUI 完全加载需要几秒钟。

## 使用说明

我们只在 macOS 上的 Google Chrome 和 Safari 上测试 UI。它可能在其他浏览器上也能工作 — 也可能不能。如果您在使用不同的浏览器并需要支持，请确保提前提到这一点，或者更好的是，先在 Chrome/Safari 上尝试。

> :white_check_mark: **提示**：如果您的计算机 RAM 为 8 GB 或更少，请使用 `node platform minMemo` 以最小 RAM 要求运行系统。

# :small_orange_diamond: 卸载

Superalgos 除了快捷方式文件外，不会在 `Superalgos` 文件夹之外写入任何内容。要快速删除快捷方式文件，打开终端或命令提示符，导航到您的主 Superalgos 目录，并输入以下命令：

```sh
node uninstall
```

然后只需删除 `Superalgos` 文件夹即可完全删除应用程序。

# :small_orange_diamond: 联系我们！

> :warning: **当心冒充者 — 骗子正在潜伏！**
>
> Superalgos 管理员、创始团队和社区版主永远不会主动联系您，除非您先联系他们。我们永远不会要求您提供 API 密钥、代币或现金。我们永远不会要求您以任何方式信任我们。我们的[社区安全政策](https://superalgos.org/community-safety-policy.shtml)解释了原因。
> 
> **简而言之，我们想要明确表示，如果有人主动联系您声称为项目工作或与项目合作，这就是一个骗局。**
>
> 请在社区群组中报告骗子，以便将其封禁并提高对这个问题的认识，同时也要将其拉黑并向 Telegram 报告（如果有此选项）。

我们刚刚开设了一个全新的[支持和社区 Discord 服务器](https://discord.gg/CGeKC6WQQb)。

话虽如此，支持问题在 [Support Telegram 群组](https://t.me/superalgossupport)中往往能得到更快的回应。

我们也在其他 [Telegram 群组](https://superalgos.org/community-join.shtml)见面，这就是一切开始的地方！

# :small_orange_diamond: 其他资源

- 网站

  - 要了解 Superalgos 能为您做什么，请查看 [Superalgos 网站](https://superalgos.org/)。

  - [社区资源列表](https://superalgos.org/community-resources.shtml)，包括文字、视听和交互式内容。

- Telegram

  - 获取官方新闻，加入 [Superalgos 公告频道](https://t.me/superalgos)。

  - 在 [Superalgos Telegram 社区群组](https://t.me/superalgoscommunity)中认识其他用户。

  - 在 [Superalgos Telegram 开发者群组](https://t.me/superalgosdevelop)中认识开发者。

  - 用户在其他特定主题的 Telegram 群组中见面。网站上有[完整的群组列表](https://superalgos.org/community-join.shtml)。

- 博客：在 [Superalgos 博客](https://medium.com/superalgos)上找到官方公告和各种文章。

- Twitter：关注 [Twitter 上的 Superalgos](https://twitter.com/superalgos)以保持联系。帮助我们传播消息！

- Facebook：关注 [Facebook 上的 Superalgos](https://www.facebook.com/superalgos)。

# :small_orange_diamond: 贡献

Superalgos 是一个由用户为用户构建的社区项目。了解[如何贡献](https://superalgos.org/community-contribute.shtml)。

# :small_orange_diamond: 许可证

Superalgos 是在 [Apache License 2.0](LICENSE) 下发布的开源软件。

<hr>
<hr>
<hr>
<hr>
<hr>

# 附录

# :small_orange_diamond: 前提条件说明

## Windows 前提条件

在按照 Windows 安装程序安装 Git 时，确保遵循所有推荐和默认设置非常重要，特别是在下面这一步：

![IMG_0764](https://user-images.githubusercontent.com/55707292/189213902-7f7b3642-545f-47a7-89fc-3c45971c885d.jpg)

### 可选的 Windows 前提条件

对于想要测试（部分和不完整的）TensorFlow 集成的 Windows 用户，您需要安装 Python。

- [安装 Python 3.9](https://www.python.org/downloads/release/python-390/)。

Github Desktop 是管理 Git 冲突和问题的有用工具。您可以使用以下链接安装它。

- [GitHub Desktop 下载页面](https://desktop.github.com/)。点击"Download for Windows"按钮，下载完成后按照向导安装。

## Mac OS 前提条件 Homebrew 安装

除了手动安装 NodeJS、Git 和 Python 之外，[Homebrew](https://brew.sh/) 可以用来以最小的努力在 Mac OS 上安装前提条件。克隆仓库后，将目录更改为 Superalgos 基础目录，并使用 Homebrew 安装要求。

使用 Homebrew 有两种方式。第一种是输入：

```sh
brew install git node npm python@3.9
```

第二种是使用代码仓库中包含的 `Brewfile`。下载后，在 `Brewfile` 所在的同一目录中运行此命令：

```sh
brew bundle
```

> :white_check_mark: **注意**：您可以使用 Safari 或 Google Chrome 作为默认浏览器。如果您在 Safari 中遇到错误，将被要求在 Chrome 中重现它，因为开发团队使用 Chrome。

## Linux（例如 Debian、Ubuntu 或运行 Raspberry Pi OS 的树莓派）前提条件

当使用已经包含 Node.js 版本 >= 16 的 Linux 发行版时，安装 Superalgos 最容易。我们成功测试了以下发行版：

* Debian 版本 >= 12（"Bookworm"）
* Fedora 版本 >= 39
* Rocky Linux >= 9
* AlmaLinux >= 9

对于基于 Debian 的发行版（例如 Debian、Ubuntu），运行以下命令安装所需的依赖项：

```sh
apt-get install nodejs npm git
```

当使用面向 RHEL 的发行版（例如 Fedora、CentOS、Rocky Linux、AlmaLinux）时，运行以下命令安装所需的依赖项：
```sh
dnf install nodejs git
```

[许多其他发行版](https://nodejs.org/en/download/package-manager/)的 Node.js 安装说明也是可用的。

> :white_check_mark: **注意**：您需要在系统上有足够的权限来安装新软件包。可能需要在上述命令前加上 **sudo** 才能使其工作。
>
> :white_check_mark: **注意**：虽然某些发行版将 **npm** 与 **node** 打包在一起，但其他发行版需要单独安装 **npm**。
>
> :white_check_mark: **注意**：您可以额外安装 "python3" 包。Python 3 仅用于测试（部分和不完整的）TensorFlow 集成。


您现在可以使用这些命令验证成功安装和已安装的软件版本：

```sh
node -v
npm -v
git --version
```

所有三个命令都应该成功执行并返回版本号。如果 node 的版本号 < 16，请按照下面的说明[设置更新版本的 Node.js](#installing-newer-versions-of-nodejs)。在撰写本文时，特别是 **Ubuntu 用户**将需要执行这些额外步骤，因为 Ubuntu 附带的 node 版本已过时。

如果您想在不同于标准 PC 的 x86 芯片组的机器上运行 Superalgos，例如在基于 ARM 的机器上，请确保安装[非标准芯片组的额外前提条件](#additional-prerequisites-for-non-standard-chipsets)。

成功安装所有前提条件后，继续获取您的 [Github 个人访问令牌](#two-get-your-githubcom-personal-access-token)并继续 Superalgos 平台客户端安装。

### 安装更新版本的 Node.js
使用附带过时版本 Node.js 的 Linux 发行版（例如 Ubuntu）的用户将需要手动安装更新版本的 Node.js。我们建议使用 Node Version Manager (nvm) 来完成此操作。要安装 nvm，执行以下命令之一（取决于您系统上是否有 curl 或 wget）：
```sh
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh | bash
```
或
```sh
wget -qO- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh | bash
```
> :white_check_mark: **重要提示**：
> 
> 安装 nvm 后，您需要关闭当前终端并打开一个新终端（注销并重新登录）才能使安装生效。

成功设置 nvm 后，您现在可以通过运行 **nvm install**，后跟您想要设置的版本号，轻松获取更新版本的 node。例如，要安装 Node.js v20：
```sh
nvm install 20
```
最后但同样重要的是，检查 node 的活动版本是否现在满足您的需求：
```sh
node -v
```


### 非标准芯片组的额外前提条件
运行**不同于标准 PC (x86)** 芯片组的机器的用户，例如基于 arm64 的机器的用户，还需要安装 **make、gcc 和 g++** 才能成功完成设置过程。

对于运行在非 x86 芯片组机器上的基于 Debian 的发行版（例如 Debian、Ubuntu）：
```sh
apt-get install build-essential
```
对于运行在非 x86 芯片组机器上的面向 RHEL 的发行版（例如 Fedora、CentOS、Rocky Linux、AlmaLinux）：
```sh
dnf install make gcc gcc-c++
```
对于任何其他发行版，请调查 **make、gcc 和 g++** 的包名称并相应地安装这些包。


# :small_orange_diamond: 依赖安装故障排除

## 边缘情况

> :white_check_mark: **WINDOWS 用户安装 TENSORFLOW 依赖项的注意事项：** 您可能在设置过程结束时遇到错误。如果遇到，请按照错误消息后的说明操作。

> :white_check_mark: **在同一台机器上安装多个 SUPERALGOS 实例的用户注意事项：** 为避免快捷方式之间的名称冲突，请确保在运行 `node setup shortcuts` 之前重命名每个 Superalgos 目录。

> :white_check_mark: **在 LINUX 上安装的用户注意事项：** 如果在运行 `node setup` 后提示您通过运行 'npm audit fix' 解决问题，请忽略此步骤。

> :white_check_mark: **在具有非标准芯片组的 LINUX 机器上安装的用户注意事项：** 如果在运行 `node setup` 后收到指向缺少 make、cc 或 gcc 等应用程序的错误消息，请查看[非标准芯片组的额外前提条件](#additional-prerequisites-for-non-standard-chipsets)。

> :white_check_mark: **在 1GB RAM 计算机上安装的用户注意事项** Superalgos 刚刚超出了只有 1GB RAM 的计算机的能力。例如，树莓派 3 确实可以运行入门教程，但随着时间推移（到 2023 年），这可能会显著变慢，甚至可能停止。如果您仍然希望使用只有 1GB RAM 的计算机（您已经被警告过），您将需要使用 Node.js 的 16.x 版本，因为 18.x 版本在设置期间需要远超过 1 GB 的 RAM。

## 一般故障排除

如果您在运行 node setup 命令时遇到困难，这里有一些可能妨碍您的常见问题。

1. 检查您安装的 node 和 npm 版本。确保您运行的是大于 16.6 版本的 node 和大于 5 版本的 npm 的更新版本。您可以通过在命令提示符或终端中输入 `node -v` 和 `npm -v` 来检查您有哪个版本。如果您的版本号低于这些，您可以按照上面"Node JS 安装"步骤中概述的说明更新您的安装。

2. 如果您在管理保护的目录中安装 Superalgos，您需要执行以下操作之一：

   - 对于 Windows，以管理员身份启动命令提示符。

   - 对于 Linux 和 Mac 系统，确保在 node setup 前添加 sudo 命令。这将看起来像 `sudo node setup`。

3. 对于 Windows，重要的是您已将 C:\Windows\System32 添加到全局 PATH 中。有关如何执行此操作的说明，请搜索"在 Windows 10 中添加到 PATH"。

4. 如果您在 node setup 期间收到很多"意外"错误，请尝试在再次运行 `node setup` 之前使用命令 `npm ci --omit=optional` 重置 npm。

## 在 Ubuntu 中启用桌面快捷方式

大多数安装的快捷方式都可以开箱即用。然而，Ubuntu 上的桌面快捷方式需要一些额外的步骤来设置。首先，需要在 Tweaks 应用程序中启用桌面图标。

- 检查是否安装了 Tweaks。

- 如果没有，转到 Ubuntu Software。

- 安装 Tweaks。

- 打开 Tweaks。

- 在扩展下打开桌面图标

![enable-ubuntu-shortcut](https://user-images.githubusercontent.com/55707292/117553927-f0780300-b019-11eb-9e36-46b509653283.gif)

> :white_check_mark: **提示：** 如果您没有立即看到桌面快捷方式出现，您可能需要重启计算机。

最后，您需要启用桌面快捷方式。右键点击 Superalgos.desktop 并选择允许启动。

![allow-launching](https://user-images.githubusercontent.com/55707292/117553933-fcfc5b80-b019-11eb-872c-4fad81b184d2.gif)

现在启动器和桌面快捷方式都可以像计算机上的任何其他程序一样启动 Superalgos。

# :small_orange_diamond: WSL2 VSCode IDE 环境设置

VSCode 是一个流行的 IDE。这个简短的部分介绍了一些有关设置 IDE 开发环境的有用提示。

有一些需要配置的内容才能从 VSCode 获得完整的功能。这些配置将使运行 ML/AI 算法的笔记本成为可能，并将 VSCode 和 Windows 转变为使用 Superalgos 的开发工作台。

在 Windows 上：

- 首先，您需要安装 WSL 和 WSL2 [https://docs.microsoft.com/en-us/windows/wsl/install](https://docs.microsoft.com/en-us/windows/wsl/install)，如果提示则重启。

  - 在继续之前，您可能还想查看 VSCode 的 Docker WSL2 后端信息。[https://aka.ms/vscode-remote/containers/docker-wsl2](https://aka.ms/vscode-remote/containers/docker-wsl2)

  - 从 Windows Store 安装 Debian 或 Ubuntu，按照说明设置 VM。
  
在 Windows 和 Debian 上：

为了使管理这些 WSL 实例变得更容易，我们现在将转向安装 VSCode + 工具，以允许 Docker 化和快速部署，以及编辑和管理您创建和贡献的 Superalgos 编辑和 fork 的测试/使用案例。

- 安装 VSCode [https://code.visualstudio.com/docs/?dv=win64user](https://code.visualstudio.com/docs/?dv=win64user)

  - 为 Visual Studio Code 安装远程容器和远程 docker 插件/扩展 [https://code.visualstudio.com/docs/remote/containers#_installation](https://code.visualstudio.com/docs/remote/containers#_installation) 

    - _您可能想花时间阅读他们网站上的这个文档的具体内容。_ 
    
  - *当提示时* 安装右键选项的 shell 快捷方式，这样您就可以在 VSCode 中轻松打开 Superalgos。

> :white_check_mark: **重要提示**：
> 
> 如上所述，如果您使用的是 Debian，您需要从系统中删除 node.js/node 并安装 NVM。
> 请参考上面关于在 Debian 系统上正确设置 node.js 和 npm 的版本问题的信息。

一旦安装完成，您现在可以使用 VSCode 作为交互式 IDE/Shell 来访问 SuperAlgos，运行 Docker 以使用 Superalgos 等。

# :small_orange_diamond: 在无头 Linux 服务器上作为守护进程运行 Superalgos

如果您在无头 Linux 服务器（如树莓派）上运行 Superalgos，您可能希望将其作为守护进程运行，这样它就不会附加到您当前的登录会话。最简单、最标准的方法可能是使用 `systemd`。大多数 Linux 发行版都使用它作为默认的 init 系统/服务管理器。

创建一个如下所示的 `superalgos.service` 文件（将 `<user>` 更改为您的用户名，将 `/path/to/Superalgos` 更改为您的 Superalgos 文件夹，例如 `/home/John/Superalgos`）：

```ini
[Unit]
Description=Superalgos Platform Client

[Service]
Type=simple
User=<user>
WorkingDirectory=/path/to/Superalgos
ExecStart=/usr/bin/node platform minMemo noBrowser

[Install]
WantedBy=multi-user.target
```

不需要以 root 身份运行 Superalgos，所以我们以用户身份运行它。`minMemo` 选项假设您在像树莓派这样的小型机器上运行，而 `noBrowser` 对于守护进程运行是有意义的。现在，您需要将文件移动到 `/etc/systemd/system/` 以便被识别。然后您需要启用并启动服务。

```sh
sudo mv superalgos.service /etc/systemd/system
sudo systemctl daemon-reload
sudo systemctl enable superalgos
sudo systemctl start superalgos
```
要检查服务状态
```sh
sudo systemctl status superalgos
```
要停止服务：
```sh
sudo systemctl stop superalgos
sudo systemctl disable superalgos
```

要查看 Superalgos 的输出，使用：

```sh
journalctl -u superalgos
```

或使用 `-f` 跟随输出：

```sh
journalctl -u superalgos -f
```