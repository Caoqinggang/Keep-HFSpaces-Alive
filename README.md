# Hugging Face Space Keep Alive (多 Space + Telegram 通知版)

这是一个 GitHub Actions 脚本，用于防止 Hugging Face Spaces 进入休眠状态（Sleep Mode）。

## ✨ 功能
1. **多 Space 支持**：在配置文件中列表式管理，一次唤醒多个。
2. **Telegram 通知**：唤醒成功或失败都会推送到手机。
3. **支持私有 Space**：兼容 Private Space（需配置 Token）。

## 🚀 使用步骤

### 1. 配置 GitHub Secrets (变量)
在仓库的 `Settings` -> `Secrets and variables` -> `Actions` 中添加：

| Name | Value | 获取方式 |
| :--- | :--- | :--- |
| `TG_TOKEN` | `123456:ABC...` | Telegram 搜索 `@BotFather` -> `/newbot` |
| `TG_ID` | `123456789` | Telegram 搜索 `@userinfobot` 查看 ID |
| `HF_TOKEN` | `hf_xxxx...` | (仅私有Space需要) Hugging Face 设置 -> Access Tokens |

### 2. 修改 Space 列表
编辑 `.github/workflows/keep_alive.yml`，找到 `matrix.url` 部分，填入你的 Space 链接。
*推荐使用 Embed 里的 Direct URL (例如 `https://user-space.hf.space`)，效果更好。*

### 3. 手动测试
进入仓库的 `Actions` 页面，点击左侧 `Keep Spaces Alive...`，再点击右侧 `Run workflow` 按钮进行测试。
