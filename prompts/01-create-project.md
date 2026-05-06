请在 `../doubao-app` 目录下创建一个 Next.js 项目，并完成初始配置。

## 步骤

### 1. 创建项目目录并初始化 Next.js

在上一级目录下创建 `doubao-app` 文件夹（即 `../doubao-app`），在其中运行以下命令初始化 Next.js 项目：

```bash
npx create-next-app@latest . --typescript --tailwind --eslint --app --import-alias "@/*" --use-npm --no-src-dir
```

### 2. 安装额外依赖

```bash
npm install openai lucide-react
```

### 3. 创建目录结构

```
components/     # React 组件
lib/            # 工具函数和配置
app/api/chat/   # 聊天 API 路由
```

### 4. 配置 Tailwind 主题

修改 `tailwind.config.ts`，添加自定义颜色和圆角配置，使 UI 风格更接近豆包的柔和、圆润风格：

- 主色调：蓝色系 (#2563eb / #3b82f6 / #eff6ff)
- 圆角：使用 rounded-xl / rounded-2xl
- 背景色：浅灰 #f5f5f5

### 5. 清理默认页面

删除 `app/page.tsx` 和 `app/globals.css` 中的默认内容，保留基本结构，让页面干净无报错。

## 完成标准

- [ ] `npm run dev` 能正常启动开发服务器
- [ ] 浏览器打开 http://localhost:3000 能看到空白页面（无报错）
- [ ] 项目结构符合上述要求

请在每一步完成后告诉我做了什么，并展示关键代码。
