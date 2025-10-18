# 在 Binance 中使用 RSA 密钥

Binance 现在支持在其 API 中使用 RSA 加密密钥。要使用 RSA 密钥而不是之前由 Binance 生成的 HMAC 密钥，请按照以下步骤操作。

登录 Binance 后，导航到 API 管理区域

![用户下拉菜单](./Projects/Foundations/PNGs/Docs/rsa-keys/binance/binance-create-rsa-key-01.png)

在这里您可以创建一个新的密钥

![创建新密钥](./Projects/Foundations/PNGs/Docs/rsa-keys/binance/binance-create-rsa-key-02.png)

这将打开一个新的对话框模态窗口，您需要选择"自生成"选项。

![选择自生成](./Projects/Foundations/PNGs/Docs/rsa-keys/binance/binance-create-rsa-key-03.png)

这将打开一个新的对话框，要求您输入公钥。Binance 使用 PKCS#8 私钥和 X509 公钥。如果您不确定这些都是什么意思，那么请访问 Binance 提供的链接，下载密钥生成器工具并按照接下来的步骤操作。

## 生成新的密钥对

打开密钥生成工具并选择 2048 位加密选项。*Binance 不会接受 4096 位密钥。*

![生成 2048 位密钥第 1 部分](./Projects/Foundations/PNGs/Docs/rsa-keys/binance/binance-create-rsa-key-04.png)

点击"Generate Key Pair"按钮。这将在下面的输入框中创建 2 个新密钥。

![生成 2048 位密钥第 2 部分](./Projects/Foundations/PNGs/Docs/rsa-keys/binance/binance-create-rsa-key-05.png)

这些密钥现在可以保存到您的交易服务器。

我们建议将这些放在 Superalgos 目录的 **My-Secrets** 文件夹中，但您也可以将它们存储在任何您喜欢的地方。

![保存公钥](./Projects/Foundations/PNGs/Docs/rsa-keys/binance/binance-create-rsa-key-06.png)

![保存私钥](./Projects/Foundations/PNGs/Docs/rsa-keys/binance/binance-create-rsa-key-07.png)

## 使用您的密钥

现在这些已经存储好了，您需要打开公钥并复制其内容。

![复制公钥数据](./Projects/Foundations/PNGs/Docs/rsa-keys/binance/binance-create-rsa-key-08.png)

将公钥内容粘贴到 Binance 的"上传公钥"对话框模态窗口中，然后点击下一步。

![粘贴公钥数据](./Projects/Foundations/PNGs/Docs/rsa-keys/binance/binance-create-rsa-key-09.png)

为您的密钥提供一个合适的名称。

![在 Binance 中命名密钥](./Projects/Foundations/PNGs/Docs/rsa-keys/binance/binance-create-rsa-key-10.png)

现在您将被重定向回 API 管理页面，在那里您可以查看您的密钥列表。您需要编辑新密钥的限制，以"启用现货和保证金交易"。

![设置密钥权限](./Projects/Foundations/PNGs/Docs/rsa-keys/binance/binance-create-rsa-key-11.png)

现在复制 Binance 提供的 API 密钥哈希。

![复制密钥哈希](./Projects/Foundations/PNGs/Docs/rsa-keys/binance/binance-create-rsa-key-12.png)

并将其粘贴到交易所账户密钥节点的配置中作为 **codeName** 值。然后将私钥的路径设置为 **secret** 值。

![将详细信息保存到 Superalgos](./Projects/Foundations/PNGs/Docs/rsa-keys/binance/binance-create-rsa-key-13.png)

*需要注意的是，私钥需要存储在运行任务的同一服务器上，并且文件路径必须有效。路径值可以是相对路径或绝对路径*