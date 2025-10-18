# 打包应用程序安装

这是开始使用 Superalgos 最简单的方式！

这些包将 Superalgos 平台的源代码打包在一个方便的文件中。要找到这些文件，您可以访问 Superalgos 的[发布页面](https://github.com/Superalgos/Superalgos/releases)。发布分为两个主要类别。首先是大约每月发布一次的稳定版本，这些版本经过最多的测试，几乎没有 bug。其次是每晚的开发快照，提供最新的代码，但没有经过相同的严格测试。

> :white_check_mark: **注意**：如果您刚刚开始，建议先安装最新的稳定版本，然后再尝试开发快照。

一旦您选择了要安装的版本类型，您就可以找到适合您操作系统的包。每个操作系统都有自己的打包应用程序，可以在您的操作系统中原生工作。以下列表突出显示了当前可用的包：

> :white_check_mark: **重要提示：** 这些安装程序没有代码签名（这需要花钱，而 Superalgos 对所有人都是完全免费的）。因此，防病毒软件可能会将文件标记为不安全。您可以强制安装以允许包运行。在这篇[媒体文章](https://medium.com/superalgos/superalgos-packaged-application-release-8befd2895102)中可以找到更详细的解释。如果这让您感到不舒服，您可以研究其他不受此限制的安装方法。

> :white_check_mark: **关于 ASCENDEX 的注意事项：** AscendEX API 的一个问题可能会阻止"欢迎使用 Superalgos"教程按预期运行。我们建议您暂时使用回退/默认工作区。该问题已报告给交易所，目前正在调查中。


## Windows 便携式应用程序

这个包不需要安装！只需下载包 `Superalgos-win-{version}.exe` 就可以了。

所有下载的交易所数据和您保存的工作区都存储在您的默认文档文件夹（Windows 上的 My Documents）下的 `Superalgos_Data` 文件夹中。这样您可以更容易地备份数据，并且在重新安装之间不会丢失数据。

## Windows 安装包

在 Windows 上，还有一个更传统的安装程序，它会安装应用程序并为您设置正确的图标和快捷方式。这样您就可以在程序列表中有一个漂亮的条目。下载的数据存储在您的文档文件夹下的 `Superalgos_Data` 文件夹中。这样您可以更容易地备份数据，并且在重新安装之间不会丢失数据。

## macOS 镜像

macOS 用户可以选择下载 DMG 包。安装非常简单，只需下载 DMG 文件，将其复制到您的应用程序文件夹，并从终端运行 `xattr -rd com.apple.quarantine Superalgos.app`（Intel/M1）或在 `System Preferences > Security & Privacy > General > Open Anyway`（仅限 Intel）中允许应用程序！

目前有两种类型的 DMG 包。x64 变体（仅适用于基于 Intel 的 Mac），以及适用于较新的基于 Apple Silicon（M1）的机器的 ARM64 变体。所有数据都存储在用户的文档文件夹下的 `Superalgos_Data` 文件夹中。这样您可以更容易地备份数据，并且在重新安装之间不会丢失数据。

有关 Superalgos 打包安装的来龙去脉的更详细说明，请参阅这篇[媒体文章](https://medium.com/superalgos/superalgos-packaged-application-release-8befd2895102)。

## 打包安装的优缺点

打包应用程序是安装 Superalgos 平台最简单的方式。平台的所有日常功能都可以随时使用，还可以向治理系统创建和提交用户配置文件！

这种类型安装的主要缺点是在添加贡献方面有限制。从打包安装中无法提交审查、编辑和翻译文档，或进行任何类型的代码贡献。