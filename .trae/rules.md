# TRAE 开发规则

## 技术栈
- Next.js 14+ (App Router) + TypeScript
- Tailwind CSS 样式
- OpenAI SDK 调用 AI 接口
- lucide-react 图标库

## 项目结构规范
- `app/` — 页面和 API 路由（App Router 规范）
- `components/` — React 组件
- `lib/` — 工具函数和配置
- `app/api/` — API 路由

## UI 风格指南
- 参考豆包：圆角较大（rounded-xl/2xl）、柔和配色（蓝白为主）
- 消息气泡：用户蓝色背景、AI 白色背景
- 响应式设计：移动端和桌面端适配
- 使用 lucide-react 图标

## 代码规范
- 函数组件 + TypeScript 类型定义
- 使用 Tailwind CSS 类名，不使用 CSS 文件
- 组件文件名使用 PascalCase
- 工具函数文件名使用 camelCase
- 状态管理优先使用 React Context + hooks
