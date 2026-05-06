# For You — Vibe Coding 入门项目

帮助团队新人通过 AI 编程助手（TRAE IDE）构建一个仿"豆包"的 AI 对话应用，快速上手 Vibe Coding 开发流程。

## 前置准备

1. 安装 [Node.js](https://nodejs.org/) (v18+)
2. 注册 [OpenAI API](https://platform.openai.com/) 并获取 API Key
3. 安装 [TRAE IDE](https://www.trae.com.cn/)

## 操作流程

### 第 1 步：克隆仓库

```bash
git clone https://github.com/Bailipa/for_you.git
```

### 第 2 步：用 TRAE 打开项目

打开 TRAE IDE，选择 `打开文件夹`，选中刚才克隆的 `for_you` 目录。

### 第 3 步：依次执行提示词

打开 `prompts/` 目录，按编号**依次**复制每个 `.md` 文件的内容，粘贴到 TRAE 的对话窗口并发送。

| 步骤 | 文件 | 说明 |
|------|------|------|
| 1 | `01-create-project.md` | 创建项目、安装依赖、配置基础结构 |
| 2 | `02-build-chat-ui.md` | 构建聊天界面 UI |
| 3 | `03-integrate-api.md` | 对接 OpenAI API，实现对话 |
| 4 | `04-polish.md` | 打磨体验、完善细节 |

### 第 4 步：观察与学习

每执行完一步，花几分钟查看 TRAE 生成的代码，理解：
- 项目结构发生了什么变化
- 新增了哪些文件和代码
- AI 是如何实现你给出的需求的

## 说明

- 所有提示词均为 AI 辅助编程设计
- 遇到问题可以先问 TRAE，它可以帮助你排查和修复
