# 选课通系统 - 课程评价与管理平台

**一个现代化的全栈课程评价管理系统，为学生提供真实的课程反馈平台，为教师提供课程质量改进的参考依据。**

![Version](https://img.shields.io/badge/version-1.0.0-blue)
![License](https://img.shields.io/badge/license-MIT-green)
![Go](https://img.shields.io/badge/Go-1.24+-00ADD8)
![Vue](https://img.shields.io/badge/Vue-3.5+-4FC08D)
![TypeScript](https://img.shields.io/badge/TypeScript-5.8+-3178C6)

## 📋 项目概述

选课通系统是一个基于前后端分离架构的现代化课程评价平台，采用 Go + Vue 3 + TypeScript 技术栈构建。系统旨在为学生提供一个真实、透明的课程评价环境，帮助学生在选课时做出明智决策，同时为教师提供宝贵的课程改进反馈。

### 🎯 核心特性

#### 🎓 学生端功能
- **🔐 JWT认证系统**: 安全的用户注册、登录和身份验证
- **🔍 智能课程搜索**: 支持按年级、学期、科目多维度筛选
- **📊 评分可视化**: 1-5星评分系统，详细的评分分布统计
- **💬 评论互动**: 真实课程评论，支持用户间交流
- **📱 响应式设计**: 现代化 Glassmorphism UI，完美适配各种设备
- **🌟 个性化推荐**: 基于用户偏好的智能课程推荐

#### 👨‍🏫 管理员功能
- **👥 用户管理**: 完整的用户生命周期管理
- **📚 课程管理**: 课程的增删改查全功能支持
- **📈 数据统计**: 实时的课程评价数据分析和可视化
- **🛡️ 权限控制**: 基于角色的访问控制系统
- **📊 系统监控**: 完整的日志记录和系统状态监控

### 🏗️ 系统架构图

```mermaid
graph TB
    subgraph "前端层"
        A[Vue 3 学生端] --> B[Vue Router]
        A --> C[Pinia Store]
        A --> D[Axios HTTP]
        E[AdminLTE 管理端] --> F[Bootstrap 5]
    end
    
    subgraph "后端层"
        G[Go API Server] --> H[Gin Router]
        G --> I[GORM ORM]
        G --> J[JWT Auth]
        G --> K[CORS Middleware]
    end
    
    subgraph "数据层"
        L[SQLite 开发库]
        M[MySQL 生产库]
        N[Redis 缓存]
    end
    
    A --> G
    E --> G
    H --> L
    H --> M
    I --> L
    I --> M
    J --> N
```

## 🛠️ 技术栈详解

### 🎯 后端技术栈

| 技术组件 | 版本 | 说明 | 作用 |
|---------|------|------|------|
| **Go语言** | 1.24+ | 后端核心语言 | 高性能并发处理 |
| **Gin框架** | 1.9+ | HTTP Web框架 | RESTful API路由管理 |
| **GORM** | 1.25+ | ORM库 | 数据库对象关系映射 |
| **JWT** | v5.0+ | 认证库 | 用户身份验证授权 |
| **bcrypt** | latest | 密码加密 | 安全密码存储 |
| **SQLite** | 3.35+ | 开发数据库 | 本地数据存储 |
| **MySQL** | 8.0+ | 生产数据库 | 高可用数据存储 |
| **CORS** | gin-contrib | 中间件 | 跨域请求处理 |

### 🎨 前端技术栈

| 技术组件 | 版本 | 说明 | 作用 |
|---------|------|------|------|
| **Vue 3** | 3.5+ | 前端框架 | 响应式UI构建 |
| **TypeScript** | 5.8+ | 超集语言 | 类型安全保障 |
| **Vite** | 7.0+ | 构建工具 | 快速开发构建 |
| **Vue Router** | 4.5+ | 路由管理 | SPA页面导航 |
| **Pinia** | 3.0+ | 状态管理 | 全局状态管理 |
| **Axios** | 1.12+ | HTTP客户端 | API请求处理 |
| **ESLint** | 9.0+ | 代码检查 | 代码质量控制 |
| **Prettier** | 3.0+ | 代码格式化 | 代码风格统一 |

### 🎛️ 管理后台技术栈

| 技术组件 | 版本 | 说明 | 作用 |
|---------|------|------|------|
| **AdminLTE** | 4.0+ | UI框架 | 管理界面模板 |
| **Bootstrap** | 5.3+ | CSS框架 | 响应式布局 |
| **Font Awesome** | 6.0+ | 图标库 | 界面图标系统 |
| **Sass** | 1.70+ | CSS预处理 | 样式模块化管理 |
| **npm scripts** | latest | 构建工具 | 项目构建流程 |

### 🎨 UI/UX 设计系统

```css
/* 设计系统核心参数 */
:root {
  /* 主色调 - 基于 AdminLTE 品牌色 #2fa914 */
  --primary-color: #2fa914;
  --primary-light: #4fc830;
  --primary-dark: #1e7a0f;
  
  /* 渐变配色方案 */
  --gradient-primary: linear-gradient(135deg, #2fa914 0%, #4fc830 100%);
  --gradient-secondary: linear-gradient(135deg, #007aff 0%, #5ac8fa 100%);
  
  /* Glassmorphism 设计 */
  --glass-bg: rgba(255, 255, 255, 0.72);
  --glass-blur: 20px;
  
  /* 响应式断点 */
  --mobile: 768px;
  --tablet: 1024px;
  --desktop: 1200px;
}
```

## 🚀 快速开始指南

### 🖥️ 环境要求

确保您的开发环境已安装以下软件：

| 组件 | 最低版本 | 推荐版本 | 下载链接 | 验证命令 |
|------|----------|----------|----------|----------|
| **Go** | 1.18 | 1.24+ | [下载Go](https://golang.org/) | `go version` |
| **Node.js** | 16 | 20+ | [下载Node.js](https://nodejs.org/) | `node --version` |
| **npm** | 8 | 10+ | 随Node.js安装 | `npm --version` |
| **Git** | 2.0 | 最新版 | [下载Git](https://git-scm.com/) | `git --version` |

### 📥 项目克隆与初始化

```bash
# 克隆项目
git clone https://github.com/qybaihe/xuanketong.git
cd 选课通

# 查看项目结构
tree -L 2 -I 'node_modules|.git|dist'
```

**预期项目结构**:
```
选课通/
├── README.md              # 项目说明文档
├── CLAUDE.md              # Claude Code 开发指导
├── backend/               # 后端Go项目
├── frontend/              # 前端Vue项目
├── AdminLTE/              # 管理后台项目
└── .git/                 # Git版本控制
```

### 🗄️ 1. 后端服务启动

#### 🔧 步骤 1: 进入后端目录
```bash
cd backend
```

#### ✅ 步骤 2: 检查Go环境
```bash
# 检查Go版本
go version

# 检查Go模块状态
go mod verify
```

#### 📦 步骤 3: 安装依赖
```bash
# 整理Go模块依赖
go mod tidy

# 下载所有依赖
go mod download
```

#### 🚀 步骤 4: 启动后端服务
```bash
# 启动开发服务器
go run main.go
```

**✅ 预期输出**:
```bash
数据库初始化成功
GORM数据库迁移成功
Registered routes:
GET /api/v1/ping
GET /api/v1/admin-routes
[GIN] Listening and serving on :8080
```

**🌐 服务地址**: http://localhost:8080

**🧪 测试服务**:
```bash
# 在新终端窗口测试API
curl http://localhost:8080/api/v1/ping
# ✅ 预期输出: {"message":"pong"}

# 测试数据库种子数据
curl http://localhost:8080/api/v1/seed
# ✅ 预期输出: {"message":"Database seeded successfully"}
```

### 🎨 2. 前端应用启动

#### 🔧 步骤 1: 进入前端目录
```bash
cd ../frontend
```

#### ✅ 步骤 2: 检查Node.js环境
```bash
# 检查Node.js版本
node --version

# 检查npm版本
npm --version
```

#### 📦 步骤 3: 安装依赖
```bash
# 安装npm依赖
npm install

# 验证安装完成
ls node_modules
```

#### 🚀 步骤 4: 启动开发服务器
```bash
# 启动Vue开发服务器
npm run dev
```

**✅ 预期输出**:
```bash
VITE v7.0.0  ready in 320 ms

➜  Local:   http://localhost:5173/
➜  Network: http://192.168.1.100:5173/
➜  press h + enter to show help
```

**🌐 应用地址**: http://localhost:5173

### 🎛️ 3. 管理后台启动

#### 🔧 步骤 1: 进入管理后台目录
```bash
cd ../AdminLTE
```

#### 📦 步骤 2: 安装依赖
```bash
# 安装npm依赖
npm install

# 验证安装完成
ls node_modules
```

#### 🚀 步骤 3: 启动开发服务器
```bash
# 启动管理后台开发服务器
npm start
```

**✅ 预期输出**:
```bash
> admin-lte@4.0.0-rc4 start
> npm run dev

> admin-lte@4.0.0-rc4 dev
> npm-run-all --parallel watch docs-serve

...
Server running on http://localhost:3000
```

**🌐 管理后台地址**: http://localhost:3000

### 🎯 服务访问总览

| 服务 | 地址 | 说明 | 状态 |
|------|------|------|------|
| **前端应用** | http://localhost:5173 | 学生端主界面 | 🟢 运行中 |
| **后端API** | http://localhost:8080 | RESTful API服务 | 🟢 运行中 |
| **管理后台** | http://localhost:3000 | 管理员界面 | 🟢 运行中 |

### 🔄 完整开发环境启动

```bash
# 终端1 - 启动后端服务
cd backend && go run main.go

# 终端2 - 启动前端应用
cd frontend && npm run dev

# 终端3 - 启动管理后台
cd AdminLTE && npm start
```

## 📁 项目目录详解

```
选课通/
├── README.md              # 📖 项目说明文档
├── CLAUDE.md              # 🤖 Claude Code 开发指导
├── .gitignore            # 🚫 Git忽略文件配置
├── .git/                 # 📊 Git版本控制目录
│
├── 🗄️ backend/              # 后端Go项目
│   ├── main.go           # 🚪 主程序入口
│   ├── go.mod           # 📦 Go模块定义
│   ├── go.sum           # 🔒 依赖校验和
│   ├── data/             # 📂 数据目录
│   │   └── test.db     # 🗄️ SQLite数据库文件
│   ├── config/          # ⚙️ 配置文件目录
│   │   └── database.go # 🔌 数据库配置
│   ├── controllers/     # 🎮 控制器层
│   │   ├── auth_controller.go    # 🔐 认证控制器
│   │   ├── course_controller.go   # 📚 课程控制器
│   │   ├── rating_controller.go   # ⭐ 评分控制器
│   │   ├── comment_controller.go  # 💬 评论控制器
│   │   ├── admin_controller.go   # 👑 管理员控制器
│   │   └── user_controller.go    # 👥 用户控制器
│   ├── middleware/       # 🛡️ 中间件目录
│   │   └── auth.go     # 🔐 JWT认证中间件
│   ├── models/          # 📊 数据模型层
│   │   ├── user.go     # 👤 用户模型
│   │   ├── course.go   # 📚 课程模型
│   │   ├── rating.go   # ⭐ 评分模型
│   │   └── comment.go  # 💬 评论模型
│   ├── routes/          # 🛣️ 路由配置
│   │   ├── auth_routes.go     # 🔐 认证路由
│   │   ├── course_routes.go   # 📚 课程路由
│   │   ├── rating_routes.go   # ⭐ 评分路由
│   │   ├── comment_routes.go  # 💬 评论路由
│   │   ├── admin_routes.go    # 👑 管理员路由
│   │   └── user_routes.go     # 👥 用户路由
│   ├── utils/           # 🛠️ 工具函数
│   │   └── jwt.go      # 🔑 JWT工具函数
│   └── test_setup.go    # 🧪 测试数据设置
│
├── 🎨 frontend/             # 前端Vue项目
│   ├── package.json      # 📦 前端项目配置
│   ├── package-lock.json # 🔒 依赖锁定文件
│   ├── vite.config.ts    # ⚡ Vite配置文件
│   ├── tsconfig.json     # 🔧 TypeScript配置
│   ├── index.html       # 📄 入口HTML文件
│   ├── public/          # 🖼️ 静态资源目录
│   │   └── vite.svg    # ⚡ Vite图标
│   ├── src/             # 💻 源代码目录
│   │   ├── main.ts      # 🚀 主程序入口
│   │   ├── App.vue      # 🏠 根组件
│   │   ├── router/      # 🛣️ 路由配置
│   │   │   └── index.ts
│   │   ├── stores/      # 🗃️ Pinia状态管理
│   │   │   └── auth.ts  # 🔐 认证状态
│   │   ├── views/       # 📄 页面组件
│   │   │   ├── HomeView.vue        # 🏠 首页
│   │   │   ├── CourseDetailView.vue # 📚 课程详情
│   │   │   ├── AuthView.vue        # 🔐 认证页面
│   │   │   └── ProfileView.vue     # 👤 个人中心
│   │   ├── services/    # 🔌 API服务层
│   │   │   └── api.ts    # 🌐 API接口封装
│   │   ├── assets/      # 🎨 样式资源
│   │   │   └── main.css  # 🎨 全局样式
│   │   └── router/      # 🛣️ 路由守卫
│   │       └── guards.ts # 🛡️ 路由守卫
│   ├── e2e/             # 🧪 端到端测试
│   └── .vscode/         # 💻 VS Code配置
│
├── 🎛️ AdminLTE/            # 管理后台项目
│   ├── package.json      # 📦 项目配置
│   ├── package-lock.json # 🔒 依赖锁定文件
│   ├── index.html       # 📄 入口HTML文件
│   ├── tsconfig.json     # 🔧 TypeScript配置
│   ├── src/             # 💻 源代码目录
│   │   ├── scss/        # 🎨 SCSS样式文件
│   │   ├── ts/          # 📝 TypeScript文件
│   │   ├── assets/      # 🖼️ 资源文件
│   │   ├── html/        # 📄 HTML模板
│   │   └── config/      # ⚙️ 配置文件
│   ├── dist/            # 📦 构建输出目录
│   └── docs/            # 📖 文档目录
│
└── 🤖 .kilocode/          # 🤖 Kilo Code工具目录
```

## 🔄 开发工作流

### 日常开发流程

1. **启动服务**
   ```bash
   # 终端1: 启动后端
   cd backend && go run main.go
   
   # 终端2: 启动前端
   cd frontend && npm run dev
   
   # 终端3: 启动管理后台
   cd AdminLTE && npm start
   ```

2. **访问应用**
   - 前端应用: http://localhost:5173
   - 管理后台: http://localhost:3000
   - 后端API: http://localhost:8080

### 代码质量管理

#### 前端代码检查
```bash
cd frontend

# ESLint检查
npm run lint

# TypeScript类型检查
npm run type-check

# 代码格式化
npm run format

# 运行单元测试
npm run test:unit

# 运行端到端测试
npm run test:e2e
```

#### 管理后台代码检查
```bash
cd AdminLTE

# JavaScript代码检查
npm run js-lint

# CSS代码检查
npm run css-lint

# 文档检查
npm run docs-lint
```

### 构建部署

#### 前端构建
```bash
cd frontend

# 构建生产版本
npm run build

# 预览构建结果
npm run preview
```

#### 管理后台构建
```bash
cd AdminLTE

# 生产构建
npm run production
```

## 🐛 常见问题与解决方案

### 1. 端口冲突问题

**问题**: 端口被占用导致服务无法启动

**解决方案**:
```bash
# 查看端口占用
lsof -i :8080  # 后端端口
lsof -i :5173  # 前端端口
lsof -i :3000  # 管理后台端口

# 终止占用进程
kill -9 <PID>

# 或修改端口配置
# 后端端口: backend/main.go:51
# 前端端口: frontend/vite.config.ts:18
# 管理后台端口: AdminLTE/package.json:30 (docs-serve)
```

### 2. 依赖安装问题

**问题**: npm install 失败

**解决方案**:
```bash
# 清理缓存
npm cache clean --force

# 删除node_modules和package-lock.json
rm -rf node_modules package-lock.json

# 重新安装
npm install
```

### 3. Go模块问题

**问题**: go mod tidy 失败

**解决方案**:
```bash
# 初始化Go模块
go mod init xuan-ke-tong

# 整理依赖
go mod tidy

# 验证依赖
go mod verify
```

### 4. 数据库连接问题

**问题**: 数据库连接失败

**解决方案**:
```bash
# 检查数据库文件
cd backend
ls -la test.db

# 重新创建数据库
rm test.db
go run main.go
```

### 5. CORS跨域问题

**问题**: 前端访问后端API时出现跨域错误

**解决方案**:
- 确保后端CORS配置正确（backend/main.go:15-19）
- 前端代理配置正确（frontend/vite.config.ts:18-26）
- 确保后端服务正常运行

## 🌐 API接口文档

### 🔐 认证相关接口 (`/api/v1/auth`)

| 方法 | 路径 | 功能 | 权限 | 请求体 | 响应 |
|------|------|------|------|-------|------|
| `POST` | `/register` | 用户注册 | 公开 | `{username, password, email, nickname, avatar?}` | `{token, user}` |
| `POST` | `/login` | 用户登录 | 公开 | `{username, password}` | `{token, user}` |
| `GET` | `/me` | 获取当前用户 | JWT | 无 | `{user}` |

**示例请求**:
```bash
# 用户注册
curl -X POST http://localhost:8080/api/v1/auth/register \
  -H "Content-Type: application/json" \
  -d '{"username":"test","password":"123456","email":"test@example.com","nickname":"测试用户"}'

# 用户登录
curl -X POST http://localhost:8080/api/v1/auth/login \
  -H "Content-Type: application/json" \
  -d '{"username":"test","password":"123456"}'
```

### 📚 课程相关接口 (`/api/v1/courses`)

| 方法 | 路径 | 功能 | 权限 | 参数 | 响应 |
|------|------|------|------|------|------|
| `GET` | `/` | 获取课程列表 | 公开 | `?grade=年级&semester=学期&subject=科目` | `[{course, averageRating, totalRatings}]` |
| `GET` | `/:id` | 获取课程详情 | 公开 | 课程ID | `{course}` |
| `POST` | `/` | 创建课程 | 管理员 | 课程信息 | `{course}` |
| `PUT` | `/:id` | 更新课程 | 管理员 | 课程ID, 更新信息 | `{course}` |
| `DELETE` | `/:id` | 删除课程 | 管理员 | 课程ID | `{message}` |

### ⭐ 评分相关接口 (`/api/v1/ratings`)

| 方法 | 路径 | 功能 | 权限 | 请求体 | 响应 |
|------|------|------|------|-------|------|
| `POST` | `/` | 提交评分 | JWT | `{userId, courseId, score}` | `{message}` |
| `GET` | `/courses/:id/ratings` | 获取课程评分 | 公开 | 课程ID | `[{rating, user}]` |

### 💬 评论相关接口 (`/api/v1/comments`)

| 方法 | 路径 | 功能 | 权限 | 请求体 | 响应 |
|------|------|------|------|-------|------|
| `POST` | `/` | 发表评论 | JWT | `{userId, courseId, content}` | `{message}` |
| `GET` | `/courses/:id/comments` | 获取课程评论 | 公开 | 课程ID | `[{comment, user}]` |

### 👑 管理员接口 (`/api/v1/admin`)

| 方法 | 路径 | 功能 | 权限 | 响应 |
|------|------|------|------|------|
| `GET` | `/users` | 获取用户列表 | 管理员 | `[{users}]` |
| `GET` | `/users/:id` | 获取用户详情 | 管理员 | `{user}` |
| `PUT` | `/users/:id` | 管理用户 | 管理员 | `{user}` |
| `DELETE` | `/users/:id` | 删除用户 | 管理员 | `{message}` |
| `GET` | `/courses` | 获取所有课程 | 管理员 | `[{courses}]` |

### 🧪 测试数据接口

| 方法 | 路径 | 功能 | 说明 |
|------|------|------|------|
| `GET` | `/seed` | 生成测试数据 | 创建用户、课程、评分、评论的测试数据 |

**使用示例**:
```bash
# 生成测试数据
curl http://localhost:8080/api/v1/seed
# 响应: {"message":"Database seeded successfully"}
```

### 📡 响应格式标准

#### 成功响应格式
```json
{
  "data": {
    // 返回的数据
  },
  "message": "操作成功"
}
```

#### 错误响应格式
```json
{
  "error": "错误信息描述",
  "code": 400
}
```

#### 认证错误
```json
{
  "error": "未授权访问",
  "code": 401
}
```

### 🔐 JWT认证流程

1. **登录获取Token**:
   ```json
   {
     "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...",
     "user": {
       "id": 1,
       "username": "test",
       "email": "test@example.com",
       "nickname": "测试用户"
     }
   }
   ```

2. **使用Token**:
   ```bash
   curl -H "Authorization: Bearer eyJhbGciOiJIUzI1NiIs..." \
        http://localhost:8080/api/v1/auth/me
   ```

## 🤝 贡献指南

1. **Fork项目**
2. **创建功能分支** (`git checkout -b feature/AmazingFeature`)
3. **提交更改** (`git commit -m 'Add some AmazingFeature'`)
4. **推送分支** (`git push origin feature/AmazingFeature`)
5. **创建Pull Request**

### 开发规范

#### 代码风格
- **Go**: 遵循Go官方代码风格
- **Vue**: 使用Composition API，遵循Vue 3最佳实践
- **TypeScript**: 严格类型检查，避免any类型

#### 提交信息规范
```
type(scope): description

# 示例
feat(auth): add user registration feature
fix(api): resolve CORS issue in development
docs(readme): update installation instructions
```

## 📄 许可证

本项目采用 MIT 许可证 - 查看 [LICENSE](LICENSE) 文件了解详情。

## 📞 联系方式

- **项目维护者**: Baihe
- **邮箱**: [your-email@example.com]
- **GitHub**: [项目地址]

## 🙏 致谢

感谢以下开源项目的支持：
- [Vue.js](https://vuejs.org/) - 渐进式JavaScript框架
- [Gin](https://gin-gonic.com/) - Go Web框架
- [AdminLTE](https://adminlte.io/) - 管理后台模板
- [Bootstrap](https://getbootstrap.com/) - CSS框架

---

## 📖 更新日志

### v1.0.0 (2024-09-15)
- ✅ 完成基础架构搭建
- ✅ 实现用户认证系统
- ✅ 完成课程管理功能
- ✅ 实现评分和评论系统
- ✅ 搭建管理后台界面
- ✅ 添加详细的README文档

---

**注意**: 如果您在开发过程中遇到问题，请参考本文档的"常见问题与解决方案"部分，或者提交Issue寻求帮助。
