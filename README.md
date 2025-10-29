# Warp.dev Account Tool

[![GitHub release](https://img.shields.io/github/v/release/hj01857655/warpdev_account_tool)](https://github.com/hj01857655/warpdev_account_tool/releases/latest)
[![GitHub downloads](https://img.shields.io/github/downloads/hj01857655/warpdev_account_tool/total)](https://github.com/hj01857655/warpdev_account_tool/releases)
[![Platform](https://img.shields.io/badge/platform-Windows-blue)](https://github.com/hj01857655/warpdev_account_tool)

🚀 一个功能强大的 Warp.dev 账号管理工具，支持账号管理、切换和监控。

## 📥 快速下载

**🎉 最新版本: v2.0**

- 💾 **直接下载**: [WarpAccountTool.exe](https://github.com/hj01857655/warpdev_account_tool/releases/latest/download/WarpAccountTool.exe)
- 📋 **Release 页面**: [查看所有版本](https://github.com/hj01857655/warpdev_account_tool/releases)
- 📖 **使用文档**: 见下方详细说明
- 💬 **社区支持**: [加入 QQ 群 608248908](https://qm.qq.com/q/amKj8q1jIA) | [Telegram 频道](https://t.me/warp5215)

## ✨ 主要功能

### 🎯 账号管理
- **可视化界面**：基于 PySide6 的现代化 GUI
- **账号切换**：一键切换账号并自动配置
- **Token 管理**：自动刷新和管理认证令牌
- **使用限制监控**：实时查看账号使用情况
- **批量操作**：支持导入导出、批量刷新

### 🔐 注册功能 ⚠️
> **重要提示**: 自动注册功能目前暂时不可用，由于 Warp.dev 调整了注册流程，我们正在更新相关代码。当前版本主要专注于账号管理功能。

- **单账号注册**: 自动完成完整的 10 步注册流程 🙅‍♂️ 暂时不可用
- **批量注册**: 支持并发批量注册多个账号 🙅‍♂️ 暂时不可用
- **临时邮箱**: 自动生成和验证临时邮箱 🙅‍♂️ 暂时不可用
- **中断恢复**: 支持注册过程中断后恢复 🙅‍♂️ 暂时不可用

### 💾 数据管理
- **SQLite 数据库**：持久化存储账号信息
- **DPAPI 加密**：支持读写 Warp 加密数据文件
- **注册表管理**：自动管理 Windows 注册表配置
- **Experiment ID**：每次切换账号生成新的实验 ID

### 📊 高级特性
- **限流控制**：智能限流避免 API 封禁
- **错误处理**：完善的错误分类和重试机制
- **日志记录**：详细的操作日志
- **数据备份**：支持导出和备份账号数据

## 📁 项目结构

```
warpdev-batch-register/
├── main.py                      # 主入口文件
├── start.bat                    # Windows 快速启动脚本
├── pyproject.toml               # 项目配置和依赖 (uv 管理)
├── README.md                    # 项目说明
├── .gitignore                   # Git 忽略文件
│
├── src/                         # 源代码目录
│   ├── __init__.py
│   ├── warp_account_manager.py  # GUI 账号管理工具 ⭐
│   │
│   ├── core/                    # 核心功能模块
│   │   ├── __init__.py
│   │   ├── warp_single_register.py       # 单账号注册
│   │   ├── warp_async_batch_register.py  # 异步批量注册
│   │   └── warp_graphql.py               # GraphQL 客户端
│   │
│   ├── managers/                # 业务逻辑管理器
│   │   ├── __init__.py
│   │   ├── data_manager.py            # 数据库管理
│   │   └── http_manager.py            # HTTP 请求管理
│   │
│   └── utils/                   # 工具模块
│       ├── __init__.py
│       ├── config.py                  # 配置管理
│       ├── logger.py                  # 双日志系统 🆕
│       ├── registry.py                # 注册表操作
│       └── dpapi.py                   # DPAPI 数据文件管理
│
├── data/                        # 数据目录
│   └── *.json                   # JSON 数据文件
│
├── docs/                        # 文档目录
│   ├── WARP.md
│   └── WarpDev_Registration_Analysis.md
│
├── logs/                        # 日志目录
│   └── *.log                    # 日志文件
│
├── results/                     # 结果目录
│   └── warp_accounts.db         # SQLite 数据库
│
└── scripts/                     # 脚本目录
```

## 🚀 快速开始

### 方式一：直接使用可执行文件（推荐）

1. **下载**: [点击下载 WarpAccountTool.exe](https://github.com/hj01857655/warpdev_account_tool/releases/latest/download/WarpAccountTool.exe)
2. **运行**: 双击直接运行，无需安装任何依赖
3. **使用**: 在 GUI 界面中管理你的 Warp 账号
### 方式二:源码运行

1. **克隆仓库**:
```bash
git clone https://github.com/hj01857655/warpdev_account_tool.git
cd warpdev_account_tool
```

2. **安装依赖** (推荐使用 uv):
```bash
# 使用 uv (推荐 - 极快的依赖管理)
uv sync

# 或者使用传统的 pip
uv pip install -e .
```

> 💡 **什么是 uv?** [uv](https://github.com/astral-sh/uv) 是一个极快的 Python 包管理器，比 pip 快 10-100 倍。
> 安装 uv: `pip install uv` 或访问 [uv 官网](https://docs.astral.sh/uv/)

3. **运行程序**:
```bash
# 使用 uv
uv run python main.py

# 或直接使用 python
python main.py
```
```

### 主要功能介绍

👍 **当前可用功能**:
- 账号列表管理和查看
- 一键切换 Warp 账号
- Token 刷新和管理
- 使用限制监控
- 账号数据导入/导出

⚠️ **暂时不可用功能**:
- 自动注册新账号（等待更新）

## 📦 依赖项

- **PySide6** - GUI 框架
- **requests** - HTTP 请求
- **pyperclip** - 剪贴板操作
- **urllib3** - HTTP 客户端
- **sqlite3** - 数据库（Python 内置）
- **ctypes** - Windows API 调用（Python 内置）

## 🔧 配置

配置文件位于 `src/utils/config.py`，可以自定义：
- API 端点
- 并发数量
- 超时时间
- 日志级别
- 数据目录

## 💡 使用技巧

### 切换账号
1. 在账户列表中找到目标账号
2. 点击「🔀」按钮
3. 系统会自动：
   - 生成新的 ExperimentId (UUID)
   - 写入注册表 (current_user_token, ExperimentId)
   - 更新 Warp SQLite 数据库
   - 查询账号限制信息
4. **重要：切换后需要重启 Warp 应用使配置生效**

### 刷新 Token
- 单个刷新：点击账号行的「🔄」按钮
- 批量刷新：点击工具栏的「📊 刷新限制」按钮

### 导入已有账号
1. 准备 JSON 文件（格式见 `data/` 目录示例）
2. 点击「📁 导入」按钮
3. 选择 JSON 文件即可导入

### 导出账号数据
- 导出账户列表：包含基本信息
- 导出令牌：包含完整的认证信息

## 🛡️ 安全说明

- **DPAPI 加密**：使用 Windows DPAPI 保护本地数据
- **注册表管理**：仅修改 Warp 相关注册表项
- **Token 安全**：ID Token 和 Refresh Token 加密存储
- **日志脱敏**：敏感信息在日志中隐藏

## 🐛 故障排除

### 注册失败
- 检查网络连接
- 查看日志文件了解详细错误
- 尝试降低并发数

### Token 刷新失败
- 确认 Refresh Token 有效
- 检查 API 端点配置
- 查看网络代理设置

### GUI 无法启动
- 确认已安装 PySide6
- 检查 Python 版本（需要 3.8+）
- 查看控制台错误信息

## 📝 开发说明

### 添加新功能
1. 在相应的模块目录添加代码
2. 更新 `__init__.py` 导出
3. 添加单元测试
4. 更新文档

### 代码风格
- 遵循 PEP 8 规范
- 使用类型提示
- 添加文档字符串
- 保持代码简洁

## 📄 许可证

本项目仅供学习和研究使用。

## 🙏 致谢

感谢 Warp.dev 提供优秀的终端工具。

## 📞 联系与支持

## 💻 系统要求

### 最小要求
- 📟 **操作系统**: Windows 7/8/10/11 (64-bit)
- 🌐 **网络**: 稳定的互联网连接
- 💾 **存储空间**: 至少 500MB 可用空间
- 🔒 **权限**: 建议以管理员身份运行（可选）

### 推荐配置
- 💫 **内存**: 4GB 或更多
- 🔌 **网络**: 带宽 10Mbps 或更高

## 📅 版本更新

### v2.0 (2025-10-10) - 最新版本
- 🎆 **新增**: 现代化 GUI 界面设计
- 🛡️ **优化**: 提升程序稳定性和性能
- 🔧 **修复**: 修复多个已知问题
- 🚀 **打包**: 提供独立可执行文件
- ⚠️ **注意**: 自动注册功能暂时停用

### v1.0 (2024-09-22)
- 🎉 **首次发布**: 基础账号管理功能
- 🔄 **支持**: 账号切换和 Token 管理

### 💬 社区交流
- 🐥 **QQ 群**: [608248908](https://qm.qq.com/q/amKj8q1jIA)
- 📢 **Telegram 频道**: [@warp5215](https://t.me/warp5215)
- 💬 **Telegram 聊天**: [@warp1215](https://t.me/warp1215)
- 🔗 **GitHub**: [@hj01857655](https://github.com/hj01857655/)

### 🐛 问题反馈
- 📝 **提交 Issue**: [点击这里](https://github.com/hj01857655/warpdev_account_tool/issues)
- 📧 **功能建议**: [新功能请求](https://github.com/hj01857655/warpdev_account_tool/issues/new)
- 📊 **Bug 报告**: [报告问题](https://github.com/hj01857655/warpdev_account_tool/issues/new)

---

**注意**：本工具仅用于个人学习和研究，请勿用于商业用途或违反 Warp.dev 服务条款的行为。
