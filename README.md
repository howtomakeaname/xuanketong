# 选课通系统 - 项目说明

本项目是一个现代化的前后端分离的在线课程选择与管理平台，为学生提供便捷的课程信息浏览、评分和评论渠道，并为管理员提供高效的管理工具。

## 📋 项目概述

选课通系统采用微服务架构设计，包含三个核心组件：

- **后端服务**: Go 语言 RESTful API 服务器
- **前端应用**: Vue 3 + TypeScript 单页面应用（学生端）
- **管理后台**: AdminLTE Bootstrap 5 管理界面（管理员端）

### 🎯 核心特性

#### 学生端功能
- ✅ 用户注册与登录（JWT 认证）
- ✅ 课程列表浏览与智能搜索
- ✅ 课程详细信息查看
- ✅ 课程评分系统（1-5星）
- ✅ 课程评论发表与管理
- ✅ 个人中心与评论历史

#### 管理员端功能
- ✅ 用户管理（查看、禁用、删除用户）
- ✅ 课程管理（添加、编辑、删除课程）
- ✅ 评论管理（查看、删除评论）
- ✅ 数据统计与可视化
- ✅ 系统监控与日志

### 🏗️ 系统架构图

```text
   [学生浏览器]                [管理员浏览器]
        |                           |
        v                           v
[前端 (Vue 3)]              [管理后台 (AdminLTE)]
        |                           |
        +----------+      +---------+
                   |      |
                   v      v
              [后端 API (Go)]
                   |
        +----------+----------+
        |                     |
        v                     v
    [数据库]              [文件存储]
   (SQLite/MySQL)         (静态资源)
```

## 🛠️ 技术栈详情

### 后端技术栈
- **语言**: Go 1.24+
- **Web框架**: Gin (高性能HTTP Web框架)
- **ORM**: GORM (对象关系映射)
- **数据库**: SQLite (开发环境) / MySQL (生产环境)
- **认证**: JWT (JSON Web Token)
- **CORS**: gin-contrib/cors (跨域资源共享)
- **数据迁移**: GORM AutoMigrate

### 前端技术栈
- **框架**: Vue 3.5+ (Composition API)
- **构建工具**: Vite 7.0+ (极速构建工具)
- **语言**: TypeScript 5.8+ (类型安全)
- **路由**: Vue Router 4.5+ (单页应用路由)
- **状态管理**: Pinia 3.0+ (Vue 官方状态管理)
- **HTTP客户端**: Axios 1.12+ (API请求)
- **代码质量**: ESLint + Prettier (代码规范)

### 管理后台技术栈
- **UI框架**: AdminLTE 4.0+ (Bootstrap 5)
- **CSS框架**: Bootstrap 5.3+ (响应式设计)
- **JavaScript**: ES6+ (现代JavaScript)
- **构建工具**: npm scripts (自定义构建流程)
- **CSS预处理**: Sass (CSS扩展语言)
- **图标**: Font Awesome (图标库)

## 🚀 快速开始指南

### 环境要求

确保您的开发环境已安装以下软件：

| 组件 | 最低版本 | 推荐版本 | 下载链接 |
|------|----------|----------|----------|
| Go | 1.18 | 1.24+ | [下载Go](https://golang.org/) |
| Node.js | 16 | 20+ | [下载Node.js](https://nodejs.org/) |
| npm | 8 | 10+ | 随Node.js安装 |
| Git | 2.0 | 最新版 | [下载Git](https://git-scm.com/) |

### 项目克隆与初始化

```bash
# 克隆项目
git clone <项目地址>
cd 选课通

# 查看项目结构
ls -la
```

### 1. 后端服务启动

#### 步骤 1: 进入后端目录
```bash
cd backend
```

#### 步骤 2: 检查Go环境
```bash
# 检查Go版本
go version

# 检查Go模块初始化
go mod verify
```

#### 步骤 3: 安装依赖
```bash
# 整理Go模块依赖
go mod tidy

# 验证依赖安装
go mod download
```

#### 步骤 4: 启动后端服务
```bash
# 启动开发服务器
go run main.go
```

**预期输出**:
```
Registered routes:
GET /ping
GET /admin-routes
[其他注册的路由...]
[GIN] Listening and serving on :8080
```

**服务地址**: http://localhost:8080

**测试服务**:
```bash
# 在新终端窗口测试API
curl http://localhost:8080/ping
# 预期输出: {"message":"pong"}
```

### 2. 前端应用启动

#### 步骤 1: 进入前端目录
```bash
cd ../frontend
```

#### 步骤 2: 检查Node.js环境
```bash
# 检查Node.js版本
node --version

# 检查npm版本
npm --version
```

#### 步骤 3: 安装依赖
```bash
# 安装npm依赖
npm install

# 验证安装完成
ls node_modules
```

#### 步骤 4: 启动开发服务器
```bash
# 启动Vue开发服务器
npm run dev
```

**预期输出**:
```
Local:   http://localhost:5173/
Network: http://your-ip:5173/
```

**应用地址**: http://localhost:5173

### 3. 管理后台启动

#### 步骤 1: 进入管理后台目录
```bash
cd ../AdminLTE
```

#### 步骤 2: 安装依赖
```bash
# 安装npm依赖
npm install

# 验证安装完成
ls node_modules
```

#### 步骤 3: 启动开发服务器
```bash
# 启动管理后台开发服务器
npm start
```

**预期输出**:
```
> admin-lte@4.0.0-rc4 start
> npm run dev

> admin-lte@4.0.0-rc4 dev
> npm-run-all --parallel watch docs-serve

...
Server running on http://localhost:3000
```

**管理后台地址**: http://localhost:3000

## 📁 项目目录结构

```
选课通/
├── README.md              # 项目说明文档
├── CLAUDE.md              # Claude Code 开发指导
├── AGENT.md               # 系统开发文档
├── .gitignore            # Git忽略文件
├── .git/                 # Git版本控制目录
│
├── backend/               # 后端Go项目
│   ├── main.go           # 主程序入口
│   ├── go.mod           # Go模块定义
│   ├── go.sum           # 依赖校验和
│   ├── test.db          # SQLite数据库文件
│   ├── config/          # 配置文件目录
│   │   └── database.go  # 数据库配置
│   ├── controllers/     # 控制器层
│   │   ├── auth.go      # 认证控制器
│   │   ├── course.go    # 课程控制器
│   │   ├── rating.go    # 评分控制器
│   │   ├── comment.go   # 评论控制器
│   │   ├── admin.go     # 管理员控制器
│   │   └── user.go      # 用户控制器
│   ├── models/          # 数据模型层
│   │   ├── user.go      # 用户模型
│   │   ├── course.go    # 课程模型
│   │   ├── rating.go    # 评分模型
│   │   └── comment.go   # 评论模型
│   └── routes/          # 路由配置
│       ├── auth.go      # 认证路由
│       ├── course.go    # 课程路由
│       ├── rating.go    # 评分路由
│       ├── comment.go   # 评论路由
│       ├── admin.go     # 管理员路由
│       └── user.go      # 用户路由
│
├── frontend/              # 前端Vue项目
│   ├── package.json      # 前端项目配置
│   ├── package-lock.json # 依赖锁定文件
│   ├── vite.config.ts    # Vite配置文件
│   ├── tsconfig.json     # TypeScript配置
│   ├── index.html       # 入口HTML文件
│   ├── public/          # 静态资源目录
│   │   └── vite.svg     # Vite图标
│   ├── src/             # 源代码目录
│   │   ├── main.ts      # 主程序入口
│   │   ├── App.vue      # 根组件
│   │   ├── router/      # 路由配置
│   │   ├── stores/      # Pinia状态管理
│   │   ├── views/       # 页面组件
│   │   ├── components/  # 公共组件
│   │   ├── types/       # TypeScript类型定义
│   │   └── utils/       # 工具函数
│   ├── e2e/             # 端到端测试
│   └── .vscode/         # VS Code配置
│
├── AdminLTE/             # 管理后台项目
│   ├── package.json      # 项目配置
│   ├── package-lock.json # 依赖锁定文件
│   ├── index.html       # 入口HTML文件
│   ├── tsconfig.json     # TypeScript配置
│   ├── src/             # 源代码目录
│   │   ├── scss/        # SCSS样式文件
│   │   ├── ts/          # TypeScript文件
│   │   ├── assets/      # 资源文件
│   │   ├── html/        # HTML模板
│   │   └── config/      # 配置文件
│   ├── dist/            # 构建输出目录
│   └── docs/            # 文档目录
│
└── .kilocode/           # Kilo Code工具目录
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

## 📚 API接口文档

### 认证相关接口
- `POST /api/register` - 用户注册
- `POST /api/login` - 用户登录
- `GET /api/user/profile` - 获取用户信息

### 课程相关接口
- `GET /api/courses` - 获取课程列表
- `GET /api/courses/:id` - 获取课程详情
- `POST /api/courses` - 创建课程（管理员）
- `PUT /api/courses/:id` - 更新课程（管理员）

### 评分相关接口
- `POST /api/ratings` - 提交评分
- `GET /api/courses/:id/ratings` - 获取课程评分

### 评论相关接口
- `POST /api/comments` - 发表评论
- `GET /api/courses/:id/comments` - 获取课程评论
- `DELETE /api/comments/:id` - 删除评论

### 管理员接口
- `GET /api/admin/users` - 获取用户列表
- `PUT /api/admin/users/:id` - 管理用户
- `DELETE /api/admin/users/:id` - 删除用户

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
