# Warp.dev Account Tool

[![GitHub release](https://img.shields.io/github/v/release/hj01857655/warpdev_account_tool)](https://github.com/hj01857655/warpdev_account_tool/releases/latest)
[![GitHub downloads](https://img.shields.io/github/downloads/hj01857655/warpdev_account_tool/total)](https://github.com/hj01857655/warpdev_account_tool/releases)
[![Platform](https://img.shields.io/badge/platform-Windows-blue)](https://github.com/hj01857655/warpdev_account_tool)

🚀 一个功能强大的 Warp.dev 账号管理工具，支持账号管理、切换和监控。

## 📥 快速下载

**🎉 最新版本: v2.1.6**

- 💾 **直接下载**: [WarpAccountTool.exe](https://github.com/hj01857655/warpdev_account_tool/releases/latest/download/WarpAccountTool.exe)
- 📋 **Release 页面**: [查看所有版本](https://github.com/hj01857655/warpdev_account_tool/releases)
- 📖 **使用文档**: 见下方详细说明

## 💬 社区交流

- 🐥 **问题反馈QQ群**: [Warp AI Terminal 交流群](https://qm.qq.com/q/G9JBpsUiAu) | [AI CODE IDE 交流群](https://qm.qq.com/q/hQDFVP0TW8)
- 📢 **Telegram 频道**: [@warp5215](https://t.me/warp5215)
- 💬 **Telegram 聊天**: [@warp1215](https://t.me/warp1215)
- 🔗 **GitHub**: [@hj01857655](https://github.com/hj01857655/)

### 🐛 问题反馈

- 📝 **提交 Issue**: [点击这里](https://github.com/hj01857655/warpdev_account_tool/issues)
- 📧 **功能建议**: [新功能请求](https://github.com/hj01857655/warpdev_account_tool/issues/new)
- 📊 **Bug 报告**: [报告问题](https://github.com/hj01857655/warpdev_account_tool/issues/new)

## ✨ 主要功能

### 👍 当前可用功能
- ✅ **可视化界面**：基于 PySide6 的现代化 GUI
- ✅ **账号切换**：一键切换账号并自动配置
- ✅ **Token 管理**：自动刷新和管理认证令牌
- ✅ **使用限制监控**：实时查看账号使用情况
- ✅ **批量操作**：支持导入导出、批量刷新
- ✅ **在线更新**：自动检查 GitHub Releases 并一键更新
- ✅ **数据安全**：DPAPI 加密保护本地数据
- ✅ **注册表管理**：自动管理 Windows 注册表配置

### ⚠️ 暂时不可用功能
> **重要提示**: 自动注册功能目前暂时不可用，由于 Warp.dev 调整了注册流程，我们正在更新相关代码。当前版本主要专注于账号管理功能。

- 🙅‍♂️ **单账号注册**：自动完成完整的注册流程（等待更新）
- 🙅‍♂️ **批量注册**：支持并发批量注册多个账号（等待更新）

## 🚀 快速开始

1. **下载**: [点击下载 WarpAccountTool.exe](https://github.com/hj01857655/warpdev_account_tool/releases/latest/download/WarpAccountTool.exe)
2. **运行**: 双击直接运行，无需安装任何依赖
3. **使用**: 在 GUI 界面中管理你的 Warp 账号

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
- 单个刷新：在表格行上右键，选择「🔄 刷新Token」
- 批量刷新：点击工具栏的「📊 刷新限制」按钮

### 导入已有账号
1. 准备 JSON 文件（格式见 `data/` 目录示例）
2. 点击「📁 导入」按钮
3. 选择 JSON 文件即可导入

### 导出账号数据
- 导出账户列表：包含基本信息
- 导出令牌：包含完整的认证信息

## 💻 系统要求

### 最小要求
- 📟 **操作系统**: Windows 7/8/10/11 (64-bit)
- 🌐 **网络**: 稳定的互联网连接
- 💾 **存储空间**: 至少 500MB 可用空间
- 🔒 **权限**: 建议以管理员身份运行（可选）

### 推荐配置
- 💫 **内存**: 4GB 或更多
- 🔌 **网络**: 带宽 10Mbps 或更高

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
- 下载的是最新版本的 exe 文件
- 检查 Windows 版本（需要 Windows 7 及以上）
- 查看是否被杀毒软件拦截
- 尝试以管理员身份运行

## 📝 版本更新

### v2.1.6 (2025-11-16) - 最新版本
- 🐛 **修复**: 修复切换账号逻辑漏洞 - 解决账号切换时可能出现的异常情况
- 🐛 **修复**: 彻底修复 Shiboken datetime 转换错误 - 避免 datetime 对象传递给 Qt 导致的崩溃
- 🐛 **修复**: 修复 SQLite datetime 自动转换问题 - 禁用自动转换防止类型错误
- 🐛 **修复**: 修复打包后二维码图片路径 - 确保 exe 运行时正确显示二维码
- ✨ **优化**: 优化关于对话框 - 重新设计为紧凑型水平卡片布局 (550x400)
- ✨ **优化**: 优化清理功能 - 改进账号清理逻辑和桥接服务器
- ✨ **优化**: 增强日志系统 - 提升日志记录能力，便于问题排查
- ✨ **优化**: 修复账号排序 - 优化账号列表的排序逻辑
- 🎨 **界面**: 新增微信公众号 - 添加微信公众号展示和复制功能
- 🎨 **界面**: 更新社区链接 - 添加 QQ 群、咸鱼链接等社区入口
- 🎨 **界面**: 文案优化 - 将"闲鱼下单"改为"成品号下单"
- 🔧 **项目**: 统一版本号管理 - 实现真正的异步版本管理
- 🔧 **项目**: 完善项目文档 - 添加完整的版本更新记录
- 📦 **数据**: 添加账号数据文件 - 新增示例账号数据

### v2.1.5 (2025-11-06)
- 🎨 **界面优化**: 复选框样式改进，使用Unicode字符（☐/☑）替代原生QCheckBox
- 🐛 **修复**: 修复导出账号功能 - 筛选后选中导出只导出可见账号
- 🐛 **修复**: 修复清理账号功能 - 清理额度用完账户预览和执行逻辑一致
- 🐛 **修复**: 修复导出令牌不一致 - 支持优先导出选中账户
- 🐛 **修复**: 修复默认选中当前账号 - 避免误操作当前账号
- ✨ **优化**: 筛选后自动重置全选状态，避免状态混乱
- 🔧 **改进**: 统一批量操作行为，智能处理可见行

### v2.1.4 (2025-11-03)
- ✨ **新增**: 在线更新功能
  - 启动时自动检查 GitHub Releases 最新版本
  - 精美的更新提示对话框，显示版本对比和更新日志
  - 实时下载进度显示
  - 一键重启安装更新
- 🔧 **优化**: 工具栏新增“🆙 检查更新”按钮，支持手动检查
- 📦 **依赖**: 新增 packaging 库用于版本号比较
- 🐛 **修复**: 清理账户对话框复选实现与主表格统一为 Unicode 「☐/☑」，可见性一致
- 🐛 **修复**: 彻底消除 Qt Shiboken datetime 转换错误，统一在进入 UI 前转换为字符串/时间戳
- 🗑️ **变更**: 移除表格操作列中的「刷新 Token」按钮，改为通过行右键菜单或工具栏批量刷新执行
- 🎯 **体验**: 表头全选与单元格勾选交互一致，勾选为绿色「☑」高亮
- 🧹 **说明**: start.bat 的清理仅删除项目内 __pycache__/pyc 缓存，不影响系统文件

### v2.1.3 (2025-10-29)
- 🎯 **优化**: 迁移至 uv 包管理器，依赖安装速度大幅提升
- 💬 **新增**: QQ 群快捷加入功能，方便用户交流反馈
- 🧹 **恢复**: 账号清理功能，支持批量管理超额账号
- ⚡ **性能**: 从 PyInstaller 切换至 Nuitka，启动速度提升 50%+
- 🐛 **修复**: 修复数据管理器语法错误和 UI 初始化问题
- 🔧 **优化**: 禁用日志系统，减少资源占用

### v2.0 (2025-10-10)
- 🎆 **新增**: 现代化 GUI 界面设计
- 🛡️ **优化**: 提升程序稳定性和性能
- 🔧 **修复**: 修复多个已知问题
- 🚀 **打包**: 提供独立可执行文件
- ⚠️ **注意**: 自动注册功能暂时停用

### v1.0 (2024-09-22)
- 🎉 **首次发布**: 基础账号管理功能
- 🔄 **支持**: 账号切换和 Token 管理

---

**注意**：本工具仅用于个人学习和研究，请勿用于商业用途或违反 Warp.dev 服务条款的行为。
