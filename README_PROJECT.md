# Superalgos 项目结构说明文档

## 📋 项目概述

**Superalgos** 是一个免费的开源加密货币交易机器人平台，提供完整的交易自动化解决方案。

- **版本**: 1.6.1
- **许可证**: Apache License 2.0
- **主要技术栈**: Node.js, Vue.js, React, Electron
- **官网**: https://www.superalgos.org/

## 🏗️ 核心架构

Superalgos 采用模块化架构，主要由以下几个独立应用组成：

1. **Platform App** - 核心平台应用
2. **Network App** - P2P 网络节点
3. **Task Server** - 任务执行服务器
4. **Social Trading App** - 社交交易应用
5. **Dashboards App** - 数据可视化仪表板

---

## 📁 目录结构详解

### 🔷 根目录主要文件

| 文件 | 说明 |
|------|------|
| `package.json` | 项目依赖和脚本配置 |
| `Environment.js` | 环境配置（端口、路径等） |
| `manageApps.js` | 应用管理入口 |
| `platform.js` | 平台启动入口 |
| `network.js` | 网络节点启动入口 |
| `socialTrading.js` | 社交交易启动入口 |
| `dashboards.js` | 仪表板启动入口 |
| `setup.js` | 安装设置脚本 |
| `setupPlugins.js` | 插件安装脚本 |
| `uninstall.js` | 卸载脚本 |
| `loggerFactory.js` | 日志工厂 |
| `Secrets.js` | 密钥管理 |

### 🔷 核心模块目录

#### 📂 `Platform/` - 平台核心
平台的主要功能实现，包含客户端、UI 和 Web 服务器。

```
Platform/
├── Client/              # 客户端核心代码 (61个JS文件)
│   ├── 网络接口
│   ├── 数据处理
│   └── API 路由处理
├── UI/                  # 用户界面 (21个JS文件)
│   ├── 工作区管理
│   ├── 节点编辑器
│   └── 图表渲染
├── WebServer/           # Web服务器
│   ├── css/            # 样式文件
│   ├── Images/         # 图片资源
│   ├── Fonts/          # 字体文件
│   └── index.html      # 主页面
└── PlatformApp.js       # 平台应用主文件
```

**作用**：
- 提供可视化交易策略编辑器
- 管理数据挖掘和回测任务
- 提供 Web UI 界面
- 处理用户工作区

#### 📂 `Projects/` - 项目插件系统
所有功能模块的实现，采用插件化架构。

```
Projects/
├── Algorithmic-Trading/     # 算法交易
├── Bitcoin-Factory/         # 比特币工厂（机器学习）
├── Community-Plugins/       # 社区插件
├── Data-Mining/            # 数据挖掘
├── Education/              # 教程和教育资源
├── Foundations/            # 基础框架（最大模块）
├── Governance/             # 治理系统
├── Machine-Learning/       # 机器学习集成
├── Network/                # P2P网络
├── Portfolio-Management/   # 投资组合管理
├── Social-Bots/            # 社交机器人
├── Social-Trading/         # 社交交易
├── TensorFlow/             # TensorFlow集成
├── Trading-Signals/        # 交易信号
├── User-Apps/              # 用户应用
├── Visual-Scripting/       # 可视化脚本
├── Workspaces/             # 工作区模板
├── ProjectsMenu.json       # 项目菜单配置
└── ProjectsSchema.json     # 项目架构定义
```

**说明**：
- 每个项目包含独立的 UI、TS（Trading System）、SA（Server App）等模块
- 支持热插拔，可动态加载/卸载
- 社区可贡献新插件

#### 📂 `Plugins/` - 插件目录
存放所有插件的实际代码，通过 `setupPlugins.js` 从 GitHub 仓库克隆。

```
Plugins/
├── project-plugin-map.json  # 插件映射配置
└── [各个插件仓库]           # 通过setupPlugins脚本安装
```

#### 📂 `TaskServer/` - 任务服务器
执行交易任务、数据处理、指标计算等后台任务。

```
TaskServer/
├── TaskServer.js        # 任务服务器主文件
├── NodeJsProcess.js     # Node.js进程管理
└── ProcessInstance.js   # 进程实例管理
```

**功能**：
- 执行数据挖掘任务
- 运行回测
- 执行实时交易
- 计算技术指标

#### 📂 `Network/` - P2P 网络模块
实现点对点网络通信，用于节点间数据共享和信号传播。

```
Network/
├── NetwokApp.js              # 网络应用主文件
├── NetwokProfileManagerApp.js # 网络配置管理
└── TestStats.js              # 测试统计
```

**用途**：
- 节点发现和连接
- 信号广播
- 用户配置文件同步
- 去中心化数据共享

#### 📂 `Social-Trading/` - 社交交易
多种 UI 实现的社交交易功能。

```
Social-Trading/
├── Clean-UI/            # 简洁版UI (JavaScript)
├── Vue-UI/              # Vue.js实现
├── React-UI/            # React实现
├── Client/              # 客户端逻辑
└── SocialTradingApp.js  # 应用主文件
```

**特性**：
- 交易信号分享
- 跟单交易
- 社交网络集成
- 用户配置文件管理

#### 📂 `Dashboards/` - 仪表板
数据可视化和监控仪表板。

```
Dashboards/
├── Client/              # 客户端代码
├── UI/                  # Vue组件
├── DashboardsApp.js     # 应用主文件
└── webpack.config.js    # Webpack配置
```

#### 📂 `Bitcoin-Factory/` - 比特币工厂
机器学习和 AI 交易相关功能。

```
Bitcoin-Factory/
├── Dashboard/           # 专用仪表板
├── Forecast-Client/     # 预测客户端
├── Test-Client/         # 测试客户端
├── Test-Server/         # 测试服务器
├── DockerBuild/         # Docker构建配置
└── docs/                # 文档和图表
```

**用途**：
- AI模型训练
- 价格预测
- 强化学习交易策略

#### 📂 `App-Management/` - 应用管理
应用生命周期管理和进程控制。

```
App-Management/
├── Commands/
│   ├── read/            # 读取命令
│   ├── run/             # 运行命令
│   ├── stop/            # 停止命令
│   └── restart/         # 重启命令
└── Pm2Management/       # PM2进程管理
```

#### 📂 `Launch-Scripts/` - 启动脚本
各种启动和设置脚本。

```
Launch-Scripts/
├── runPlatform.js           # 启动平台
├── runSetup.js              # 运行设置
├── runSetupPlugins.js       # 安装插件
├── runUninstall.js          # 卸载
├── createShortcut.js        # 创建快捷方式
├── systemCheck.js           # 系统检查
├── launch-linux-mac.sh      # Linux/Mac启动脚本
└── launch-windows.bat       # Windows启动脚本
```

#### 📂 `Profile-Scripts/` - 配置文件脚本
用户配置文件管理命令。

```
Profile-Scripts/
├── index.js             # 主入口
├── create/              # 创建配置
├── delete/              # 删除配置
├── describe/            # 描述配置
├── list/                # 列出配置
└── update/              # 更新配置
```

#### 📂 `Docker/` - Docker 支持
容器化部署配置。

```
Docker/
├── Dockerfile
├── docker-compose.yml
└── download-plugins.sh
```

#### 📂 `Exports/` - 文档导出
导出静态文档网站的工具。

```
Exports/
└── Docs/
    ├── Scripts/         # 导出脚本
    ├── css/            # 样式
    └── js/             # JavaScript
```

### 🔷 配置和数据目录（运行时创建）

```
Platform/
├── My-Data-Storage/     # 数据存储（市场数据、指标等）
├── My-Workspaces/       # 用户工作区
└── My-Log-Files/        # 日志文件
    ├── Platform/
    ├── Network/
    ├── Tasks/
    ├── SocialTrading/
    └── Dashboards/

My-Secrets/              # 密钥存储（API密钥等）
└── ApisSecrets.json
```

---

## 🔧 主要功能模块

### 1. 数据挖掘 (Data Mining)
- 从多个交易所下载历史数据
- 支持多种时间框架
- 自动数据更新

### 2. 交易策略开发 (Strategy Development)
- 可视化策略编辑器
- 支持复杂的条件和公式
- 代码和可视化混合编程

### 3. 回测系统 (Backtesting)
- 高性能回测引擎
- 详细的性能指标
- 可视化回测结果

### 4. 实时交易 (Live Trading)
- 支持多个交易所（通过 CCXT）
- 纸上交易模式
- 实时性能监控

### 5. 社交交易 (Social Trading)
- 信号分享
- 跟单交易
- 用户声誉系统

### 6. 机器学习 (Machine Learning)
- TensorFlow 集成
- 强化学习支持
- 预测模型训练

---

## 🚀 启动流程

### 主要启动命令

```bash
# 1. 首次安装
node setup                          # 安装依赖
node setupPlugins <username> <token> # 安装插件

# 2. 启动平台
node platform                       # 标准模式
node platform minMemo               # 低内存模式
node platform noBrowser             # 无浏览器模式
node platform minMemo noBrowser     # 适合生产环境

# 3. 启动其他服务
node network                        # P2P网络节点
node socialTrading                  # 社交交易
node dashboards                     # 仪表板

# 4. 开发相关
npm run socialTradingAppDev        # Vue开发模式
npm run build                      # 构建仪表板
npm run dist                       # 打包Electron应用
```

### 访问方式

启动后访问：
- **平台 UI**: http://localhost:34248
- **社交交易**: http://localhost:33248
- **网络节点**: http://localhost:31248

---

## 🔌 插件系统

### 插件结构

每个插件项目包含：
```
Project-Name/
├── Icons/               # 图标资源
├── Schemas/            # 数据结构定义
│   ├── Docs-Nodes/    # 文档节点
│   └── App-Schema/    # 应用架构
├── UI/                 # UI模块
│   ├── Function-Libraries/
│   ├── Node-Action-Functions/
│   └── Utilities/
├── TS/                 # 交易系统模块
│   ├── Bot-Modules/
│   └── Function-Libraries/
└── SA/                 # 服务器应用模块
    └── Modules/
```

### 核心项目说明

1. **Foundations** - 基础框架
   - 最大的项目，包含 4000+ 文件
   - 提供核心数据结构和 UI 组件
   - 所有其他项目的基础

2. **Algorithmic-Trading** - 算法交易
   - 交易机器人实现
   - 策略引擎
   - 订单执行逻辑

3. **Data-Mining** - 数据挖掘
   - 数据下载器
   - 指标计算
   - 数据存储管理

4. **Governance** - 治理系统
   - 用户配置文件
   - 贡献系统
   - 代币激励

---

## 📦 依赖说明

### 核心依赖

- **ccxt**: 交易所 API 统一接口
- **web3/ethers**: 以太坊集成
- **discord.js**: Discord 机器人
- **telegraf**: Telegram 机器人
- **winston**: 日志系统
- **pm2**: 进程管理
- **ws**: WebSocket 通信
- **simple-git**: Git 操作

### 可选依赖

- **@tensorflow/tfjs-node**: TensorFlow 机器学习
- **electron**: 桌面应用支持
- **electron-builder**: 打包工具

---

## 🗂️ 数据存储结构

### 市场数据
```
Platform/My-Data-Storage/
└── Project/
    └── Data-Storage/
        └── Exchange/
            └── Market/
                └── Masters/
                    ├── One-Min/
                    ├── Multi-Time-Frame-Daily/
                    └── Multi-Time-Frame-Market/
```

### 指标数据
```
Platform/My-Data-Storage/
└── Project/
    └── Bot-Data/
        └── Trading-Bot/
            └── Indicator-Bot/
                └── Output/
```

---

## 📝 日志系统

日志按应用分类存储：

```
Platform/My-Log-Files/
├── Platform/
│   ├── combined/YYYY-MM-DD.log
│   └── error/YYYY-MM-DD.log
├── Network/
├── Tasks/
│   └── <TASK_ID>/
├── SocialTrading/
└── Dashboards/
```

日志级别：
- `debug` - 调试信息
- `info` - 一般信息（默认）
- `warn` - 警告
- `error` - 错误

---

## 🔐 安全性

### 密钥管理
所有敏感信息存储在 `My-Secrets/` 目录：
- API 密钥
- 私钥
- 访问令牌

### 配置示例
```json
{
  "secrets": [
    {
      "nodeCodeName": "github-storage",
      "apiToken": "your-github-token"
    }
  ]
}
```

---

## 🌐 网络架构

### P2P 网络类型

1. **Mainnet** - 主网
2. **Testnet** - 测试网
3. **Permissioned Network** - 许可网络

### 网络配置
在 `Environment.js` 中配置：
```javascript
SOCIALTRADING_TARGET_NETWORK_TYPE: 'P2P Network'
SOCIALTRADING_TARGET_NETWORK_CODENAME: 'Testnet'
```

---

## 🧪 测试

```bash
npm run unitTest              # 运行单元测试
npm run unitTest:coverage     # 测试覆盖率
npm run lintAll              # 代码检查
```

测试文件位置：`.tests/` 目录

---

## 📚 文档

### README 文件
- `README.md` - 主文档
- `README_Docker.md` - Docker 安装
- `README_RaspberryPi.md` - 树莓派安装
- `README_Packaged.md` - 打包应用
- `README_PublicCloud.md` - 云部署
- `README_Signals.md` - 信号系统
- `README_Logging.md` - 日志系统
- `README_Binance_RSA_Keys.md` - Binance RSA 密钥
- `README_Documentation_Export.md` - 文档导出

### 在线文档
访问 https://superalgos.org/Docs/ 查看完整文档

---

## 🛠️ 开发工作流

### 1. 贡献流程
```bash
# Fork 仓库
git clone https://github.com/YOUR_USERNAME/Superalgos
cd Superalgos
git checkout develop

# 安装依赖
node setup
node setupPlugins <username> <token>

# 创建分支
git checkout -b feature/your-feature

# 提交更改
git add .
git commit -m "Your message"
git push origin feature/your-feature

# 创建 Pull Request
```

### 2. 调试技巧
- 使用 `logLevel=debug` 启动以获取详细日志
- 查看 `My-Log-Files/` 目录中的日志
- 使用浏览器开发者工具调试 UI

---

## 🎯 常见任务

### 添加新的交易所
1. CCXT 已支持的交易所自动可用
2. 在 UI 中添加交易所节点即可

### 创建自定义指标
1. 在 Data-Mining 项目中创建指标机器人
2. 定义数据产品
3. 编写计算代码

### 开发交易策略
1. 使用可视化编辑器创建策略
2. 定义触发条件
3. 设置仓位管理规则
4. 回测验证

---

## 📞 支持和社区

- **Discord**: https://discord.gg/CGeKC6WQQb
- **Telegram**: https://t.me/superalgoscommunity
- **GitHub**: https://github.com/Superalgos/Superalgos
- **官网**: https://superalgos.org/

---

## 📄 许可证

Apache License 2.0 - 完全开源，可自由使用和修改。

---

## 🔄 版本历史

当前版本：**1.6.1**

查看 GitHub Releases 页面了解更新历史：
https://github.com/Superalgos/Superalgos/releases

---

## ⚡ 性能优化

### 低内存模式
```bash
node platform minMemo
```

### 生产环境配置
```bash
node platform minMemo noBrowser
```

### 使用 PM2 管理
```javascript
// ecosystem.config.js
module.exports = {
  apps: [{
    name: "superalgos",
    script: "platform.js",
    args: "minMemo noBrowser",
    instances: 1,
    autorestart: true
  }]
}
```

---

## 🎓 学习路径

1. **入门** - 完成内置教程
2. **数据挖掘** - 学习如何下载和管理数据
3. **策略开发** - 创建简单的交易策略
4. **回测** - 验证策略效果
5. **纸上交易** - 在模拟环境测试
6. **实盘交易** - 小额真实交易
7. **高级功能** - 社交交易、机器学习等

---

*最后更新：2025-10-18*
