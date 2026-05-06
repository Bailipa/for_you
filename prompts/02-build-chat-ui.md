请在 `../doubao-app` 项目中构建聊天界面的 UI 部分。

## 需求说明

仿照豆包/ChatGPT 的聊天界面风格，使用 Tailwind CSS 实现一个完整的聊天 UI。

### 整体布局

```
┌─────────────────────────────────────────┐
│  [侧栏]  │          聊天区域              │
│           │  ┌───────────────────────┐   │
│  历史会话  │  │  AI 消息气泡          │   │
│           │  │                       │   │
│  会话 1   │  │                       │   │
│  会话 2   │  │  用户消息气泡          │   │
│  会话 3   │  │                       │   │
│           │  │  ─── 输入框 ────────  │   │
│  [+] 新建  │  │  [输入消息...] [发送] │   │
└─────────────────────────────────────────┘
```

### 侧栏 (Sidebar)
- 显示会话列表，每个会话项显示标题
- 顶部有"新建会话"按钮 (+)
- 可以收起/展开（移动端默认收起）
- 当前选中的会话高亮显示

### 聊天区域 (ChatArea)
- 消息列表按时间顺序排列
- 用户消息：蓝色背景 (#3b82f6)，白色文字，右侧对齐，圆角 rounded-2xl
- AI 消息：白色背景，深色文字，左侧对齐，圆角 rounded-2xl
- 每条消息显示头像占位（用户：蓝色圆形图标，AI：橙色/可爱风格图标）
- 消息区域可滚动

### 输入框 (ChatInput)
- 底部固定
- 多行文本输入（支持换行）
- 发送按钮（使用 lucide-react 的 Send 图标）
- 输入时自动调整高度
- 支持 Enter 发送（Shift+Enter 换行）
- 发送后清空输入框

### 状态管理
使用 React Context 管理以下状态：
- 消息列表（Message[]）
- 当前输入内容
- 是否正在加载（loading）
- 当前会话 ID

### 组件文件
请创建以下组件文件：

1. `components/Sidebar.tsx` — 侧栏组件
2. `components/ChatArea.tsx` — 聊天区域（包含消息列表和输入框）
3. `components/MessageBubble.tsx` — 单条消息气泡
4. `components/ChatInput.tsx` — 输入框组件
5. `components/ChatLayout.tsx` — 整体布局（组合侧栏和聊天区域）
6. `lib/store.ts` — 状态管理 (Context + useReducer)
7. `types/index.ts` — 类型定义

### 类型定义

```typescript
interface Message {
  id: string
  role: 'user' | 'assistant'
  content: string
  timestamp: number
}

interface Conversation {
  id: string
  title: string
  messages: Message[]
  createdAt: number
}
```

### UI 样式要点
- 整体使用灰色背景 (#f5f5f5)
- 卡片风格，有轻微阴影 (shadow-sm)
- 响应式：移动端宽度 < 768px 时侧栏滑出式显示
- 平滑过渡动画

## 完成标准

- [ ] 侧栏、聊天区域、消息气泡、输入框均正常显示
- [ ] 输入消息并发送后，消息出现在聊天区域（当前只是本地状态，不调 API）
- [ ] 侧栏可切换会话
- [ ] 响应式布局正常
- [ ] 在 `app/page.tsx` 中使用 ChatLayout 组件

请在每一步完成后告诉我做了什么，并展示关键代码。
