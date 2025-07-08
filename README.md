# chnroutes2

自动同步 [misakaio/chnroutes2](https://github.com/misakaio/chnroutes2) 仓库的中国IP地址段列表，并自动去除注释。

## 功能特性

- 🔄 每小时自动检查源仓库更新（公共仓库无限制）
- 📝 自动下载并处理 `chnroutes.txt` 文件
- 🧹 去除以 `#` 开头的注释行和空行
- 📊 智能检测内容变化，仅在有实际更新时提交
- 🚀 支持手动触发工作流程
- ✅ 公共仓库享受无限 GitHub Actions 使用

## GitHub Actions 使用说明

### 公共仓库优势 ✨
- **无使用限制**：GitHub Actions 在公共仓库中无限制使用
- **高频更新**：每小时检查一次，确保数据及时同步
- **无额度担忧**：不用担心超出免费额度

### 当前配置
- **运行频率**：每小时检查一次
- **使用限制**：无限制（公共仓库）
- **数据更新**：最多延迟1小时

## 工作流程

1. **检查更新**: 每小时检查源仓库是否有新提交
2. **下载文件**: 如有更新，下载最新的 `chnroutes.txt` 文件
3. **处理内容**: 去除注释行和空行
4. **比较差异**: 检查处理后的内容是否与当前版本有差异
5. **提交更改**: 仅在内容有变化时提交到本仓库

## 文件说明

- `chnroutes.txt`: 处理后的中国IP地址段列表（无注释）
- `.last_sync_commit`: 记录最后同步的源仓库提交哈希

## 手动触发

可以在 GitHub Actions 页面手动触发同步工作流程：

1. 前往仓库的 Actions 页面
2. 选择 "Sync CHN Routes" 工作流程
3. 点击 "Run workflow" 按钮

## 技术细节

- 使用 GitHub Actions 实现自动化
- 通过 GitHub API 检查源仓库更新
- 使用 `grep` 命令过滤注释和空行
- 通过文件比较避免不必要的提交

## 数据来源

本仓库的数据来源于 [misakaio/chnroutes2](https://github.com/misakaio/chnroutes2)，感谢原作者的贡献。