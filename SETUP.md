# 我的 GitHub 个人主页 —— 搭建说明

本目录是一份精简、可直接使用的 GitHub Profile README 模板，基于 sun0225SUN 的项目改造而来。

## 目录结构

```
my-profile/
├── README.md                 # 主页内容（含占位符和使用注释）
├── SETUP.md                  # 本说明文件
└── .github/workflows/
    ├── snake.yml             # 贪吃蛇贡献图（免配置）
    ├── contrib.yml           # 3D 贡献图（免配置）
    ├── blog.yml              # 博客 RSS 更新（需有博客）
    └── waka.yml              # WakaTime 编码时长（需配置 Secret）
```

## 搭建步骤

> README.md 已根据你的主页信息（用户名 `Lee-xin-hello`、昵称 lynnoli、AI Agent Developer @ Tencent）填好，无需再替换用户名，直接上传即可。

### 第 1 步：创建同名仓库
GitHub 有个特性：**仓库名 = 你的用户名**时，该仓库的 README 会显示在你的主页顶部。

- GitHub 右上角 → New repository
- Repository name 填写 **`Lee-xin-hello`**（必须与用户名完全一致，区分大小写）
- 选择 `Public`，勾选 `Add a README file`
- 创建成功后会看到 "You found a secret!" 提示

### 第 2 步：上传本目录的文件
把 `README.md` 和 `.github/` 文件夹上传到 `Lee-xin-hello/Lee-xin-hello` 仓库根目录。

### 第 3 步（可选）：微调个人信息
README 已填好，如需调整可改这些地方：
- 顶部打字机文字（`lines=` 后面的内容）
- About Me 的自我介绍
- Tech Stack 徽章（用不到的整行删掉）

### 第 5 步：配置 Secrets（可选，按需）
仓库 → Settings → Secrets and variables → Actions → New repository secret

| Secret 名 | 用途 | 获取方式 |
|-----------|------|----------|
| `GH_TOKEN` | WakaTime 工作流 | GitHub → Settings → Developer settings → Personal access tokens（勾 `repo`、`read:user`） |
| `WAKATIME_API_KEY` | WakaTime 编码时长 | 注册 wakatime.com → 账户设置里获取 |

> snake.yml 和 contrib.yml **无需任何配置**，用的是 GitHub 自动提供的 `GITHUB_TOKEN`。

### 第 6 步：手动触发一次
仓库 → Actions → 选择对应的 workflow → Run workflow。
首次运行后就会生成 `profile-snake-contrib/` 和 `profile-3d-contrib/` 目录里的图片。

之后每天 UTC 00:00 会自动更新。

## 不需要的功能怎么删？

- 不写博客：删除 `blog.yml`，并删掉 README 里 About 下的 `Recent Blog` 整块
- 不用 WakaTime：删除 `waka.yml`，并删掉 README 里 `WakaTime` 整块
- 只想要最简版：只保留 `snake.yml` + `contrib.yml`，其余图表用的是第三方免配置服务（github-readme-stats 等），直接改用户名即可

## 常见问题

- **图片显示不出来？** 检查用户名是否全部替换正确；Actions 是否已成功运行过一次。
- **Actions 报权限错误？** 仓库 Settings → Actions → General → Workflow permissions 选 `Read and write permissions`。
- **想换主题/颜色？** 各图表 URL 里的 `theme=` 参数可自行调整，可选主题见对应项目文档。
