# apps-privacy

各 iOS 应用的**隐私政策**与**支持页面**统一托管仓库（GitHub Pages）。应用 Xcode 工程与源代码保留在**私有仓库**；本仓库仅公开 App Store 所需的合规网页。

> 本仓库由原 `mybook--privacy`（值物单应用 Pages）重命名并扩展为多应用结构。若你曾在 App Store Connect 填写旧 URL，请更新为下表中的新地址。

## 在线地址总览

| 应用 | 页面 | URL |
|------|------|-----|
| **值物 (Zhizu)** | 隐私政策（简体中文） | https://wujianrenn.github.io/apps-privacy/zhizu/ |
| 值物 | 隐私政策（English） | https://wujianrenn.github.io/apps-privacy/zhizu/en.html |
| 值物 | 支持（简体中文） | https://wujianrenn.github.io/apps-privacy/zhizu/support.html |
| 值物 | 支持（English） | https://wujianrenn.github.io/apps-privacy/zhizu/support-en.html |
| **栖记 (QiJi)** | 隐私政策（简体中文） | https://wujianrenn.github.io/apps-privacy/qiji/ |
| 栖记 | 隐私政策（English） | https://wujianrenn.github.io/apps-privacy/qiji/en.html |
| 栖记 | 支持（简体中文） | https://wujianrenn.github.io/apps-privacy/qiji/support.html |
| 栖记 | 支持（English） | https://wujianrenn.github.io/apps-privacy/qiji/support-en.html |

站点首页（应用列表）：https://wujianrenn.github.io/apps-privacy/

## 目录结构

```
apps-privacy/
├── README.md
├── index.html          # 站点首页：列出所有应用及链接
├── zhizu/              # 值物
│   ├── index.html      # 隐私政策（简体中文）
│   ├── en.html
│   ├── support.html
│   └── support-en.html
└── qiji/               # 栖记
    ├── index.html
    ├── en.html
    ├── support.html
    └── support-en.html
```

各应用子文件夹内的 HTML **互相使用相对路径**（如 `en.html`、`support.html`），便于在子路径下托管。

## GitHub Pages 设置

1. 仓库须为 **Public**（私有仓库的免费 Pages 受限；合规页需公开可访问）。
2. **Settings → Pages**
   - **Source**：Deploy from a branch
   - **Branch**：`main`
   - **Folder**：`/ (root)`
3. 推送 `main` 后等待数分钟，访问 https://wujianrenn.github.io/apps-privacy/

若仓库刚从 `mybook--privacy` 重命名，GitHub 通常会将 Pages 绑定到新名称；若 404，请重新保存一次 Pages 设置。

## 从各应用私有仓库更新页面

源码中的 Markdown/HTML 模板在各应用仓库内维护，发布时复制到本仓库对应子文件夹：

| 应用 | 私有仓库中的源路径（示例） |
|------|---------------------------|
| 值物 | `zhizu/privacy/`、`zhizu/support/` |
| 栖记 | `QiJi/privacy/`、`QiJi/support/` |

典型流程（以栖记为例）：

```bash
# 在应用仓库中编辑 privacy/support 源文件后：
cp privacy/zh/index.html   /path/to/apps-privacy/qiji/index.html
cp privacy/en/index.html   /path/to/apps-privacy/qiji/en.html
cp support/zh/index.html /path/to/apps-privacy/qiji/support.html
cp support/en/index.html /path/to/apps-privacy/qiji/support-en.html

cd /path/to/apps-privacy
git add qiji/
git commit -m "Update QiJi privacy and support pages"
git push origin main
```

值物将 `zhizu/` 替换为上述 `qiji/` 路径即可。

## 新增一个应用

1. 在本仓库 `main` 上新建子文件夹，例如 `myapp/`。
2. 放入四个页面（或至少隐私政策中英文）：`index.html`、`en.html`、`support.html`、`support-en.html`。
3. 页内链接使用**同目录相对路径**。
4. 更新根目录 `index.html` 与本 `README.md` 的 URL 表。
5. 在 App Store Connect 填写：`https://wujianrenn.github.io/apps-privacy/myapp/` 等。

## App Store Connect

- **隐私政策 URL**：各语言可填对应 `index.html` 或 `en.html` 的完整 HTTPS 地址。
- **支持 URL**：填 `support.html` / `support-en.html`。
- **值物**：若曾使用 `https://wujianrenn.github.io/mybook--privacy/...`，请改为 `.../apps-privacy/zhizu/...`。

## 历史与可清理的仓库

- 原仓库名：`wujianrenn/mybook--privacy` → 现为 **`wujianrenn/apps-privacy`**。
- 若曾单独创建 **`wujianrenn/qiji`** 仅用于 Pages，可在确认新 URL 生效后自行删除该仓库（可选）。

## 许可与联系

页面内容由各应用开发者维护。联系邮箱见各支持页面。
