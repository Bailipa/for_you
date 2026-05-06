请在 `../doubao-app` 项目中对接 OpenAI API，实现真实的 AI 对话功能。

## 需求说明

### 1. 配置环境变量

创建 `.env.local` 文件，添加 API Key 配置：

```
OPENAI_API_KEY=你的OpenAI API Key
OPENAI_BASE_URL=https://api.openai.com/v1
```

> 注意：如果需要使用国内代理，请替换 OPENAI_BASE_URL 为代理地址
> `.env.local` 已在 `.gitignore` 中，不会被提交到 git

### 2. 创建 API 路由

创建 `app/api/chat/route.ts`，实现 POST 接口：

- 接收参数：`messages`（消息历史数组）
- 使用 OpenAI SDK 调用 chat.completions.create，开启 `stream: true`
- 使用流式响应返回（Edge Runtime）
- 返回格式 SSE (Server-Sent Events)
- system prompt：`你是一个有用的AI助手，名字叫"小豆"。请用中文回答用户的问题。`

### 3. 更新前端

创建 `lib/api.ts` — API 调用函数：

- 接收消息历史，调用 `/api/chat` 接口
- 处理流式响应，逐字更新 UI（打字机效果）
- 返回完整的 AI 回复内容

更新 `lib/store.ts`：

- 添加 `sendMessage` action
- sendMessage 流程：添加用户消息 → 设置 loading → 调用 API → 逐字追加 AI 回复 → 取消 loading
- 处理错误状态（API 调用失败时显示错误提示）

### 4. 持久化 (localStorage)

- 每次 AI 回复完成后，将当前会话的消息保存到 localStorage
- 刷新页面后恢复最近的会话和消息
- 侧栏显示保存的会话列表

### 5. 体验优化

- AI 回复时输入框禁用，显示 "AI 正在回复..."
- 输入框底部显示 loading 动画（三个跳动的小点）
- 如果 API 调用失败，显示错误消息和一个"重试"按钮

## 完成标准

- [ ] 配置 API Key 后能正常发送消息并收到 AI 回复
- [ ] 流式输出，打字机效果逐字显示
- [ ] 刷新页面后历史消息不丢失
- [ ] 错误状态有提示和重试功能
- [ ] `.env.local` 未提交到 git

请在每一步完成后告诉我做了什么，并展示关键代码。
