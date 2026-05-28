# Kimi Code 迁移启动 Prompt

给 Kimi Code（或 Cursor/VS Code Copilot）用的项目启动提示。

## 使用方法

1. 在 Kimi Code 中新建对话
2. 粘贴下面内容
3. 根据当前任务替换 `[任务]` 部分

## 启动 Prompt

```
我是 AIHues 项目的开发者，需要继续推进这个项目。

项目仓库：https://github.com/vastralan2001/ai-hues-v6
当前版本：v8.4，包含以下已完成内容：
- v7.7: 52 个工具页统一暖琥珀色调
- v7.8: 日历幸运签接入全局积分系统
- v7.9: 游戏页面积分显示优化
- v8.0-8.1: 积分消耗确认弹窗 + credit.js 修复
- v8.2: i18n 系统重写（字典驱动 EN/ZH 切换）
- v8.3: 新 Logo（机器人×彩虹弧）全站替换
- v8.4: i18n 整合 + 清理

项目上下文仓库：https://github.com/vastralan2001/aihues-context

请先读取以下文件了解完整上下文：
- https://raw.githubusercontent.com/vastralan2001/aihues-context/main/daily/2026-05-28-full.md
- https://raw.githubusercontent.com/vastralan2001/aihues-context/main/context/project-overview.md

技术栈：纯 HTML/CSS/JS（无框架），Live Server 开发
配色：暖琥珀色 #b45309 + 彩虹色 Logo
部署：GitHub Pages

工作习惯（必须遵守）：
1. 每版改动展示结果（截图/描述）后再继续
2. 大需求先预估时长
3. 不确定的地方多问，不做假设
4. 上下文快满时主动压缩迁移

当前主要任务（选一个推进）：
- 英文版 i18n 继续扩展（首页已有基础，需扩展到其他页面）
- 继续写 SEO 文章（已有 3 篇，目标再写 2-3 篇）
- Logo 精修（v4b 定稿，后续微调）

请 clone 仓库并继续推进。
```

## 环境差异说明（Kimi Code vs OpenClaw）

| 能力 | OpenClaw | Kimi Code |
|------|----------|-----------|
| 浏览器截图验证 | ✅ 内置 | ❌ 手动刷新浏览器 |
| HTTP Server | ✅ `python3 -m http.server` | ⚠️ 用 Live Server 插件 |
| 本地记忆文件 | ✅ 自动读取 | ❌ 需手动粘贴 |
| GitHub Token | ✅ 本地配置 | ⚠️ 需重新配置 |
| Git 操作 | ✅ 自动 | ✅ 手动命令 |
| 上下文压缩 | ✅ 自动迁移 | ❌ 手动复制粘贴 |

## 快速命令参考

```bash
# Clone 仓库
git clone https://github.com/vastralan2001/ai-hues-v6.git

# 启动 Live Server（VS Code 插件）
# 或手动
python3 -m http.server 3456

# 查看 Git 状态
git status
git log --oneline -5

# Push 改动
git add -A
git commit -m "vX.X: description"
git push
```

## 关键文件位置

```
ai-hues-v6/
├── index.html          # 首页（含 i18n 入口）
├── js/i18n.js          # i18n 系统（v8.2 重写）
├── js/credit.js        # 积分系统
├── logo.svg            # Logo 文件（v4b）
├── tools/              # 52 个工具页
├── games/              # 3 个游戏页
└── blog/               # SEO 文章
```

---
_创建时间: 2026-05-28_
_版本: v8.4_
