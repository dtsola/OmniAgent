# OmniAgent AI Agent 开发教学平台 - AI 协作开发规范

> **版本**: v1.0  
> **创建日期**: 2026-05-14  
> **项目类型**: 教学项目 / AI Agent 平台  
> **技术栈**: FastAPI + Vue 3 + LangChain  
> **当前版本**: v2.4.0  
> **项目状态**: ✅ MVP 已完成 (100%)

---

## 📌 项目概述

OmniAgent 是一个面向 AI 工程学习者的完整 AI Agent 开发教学平台，包含 7 种 Agent 类型、完整的 RAG 系统、MCP 协议支持、工具管理等功能。

**核心特性：**
- ✅ 7 种 Agent 类型（General、React、Plan-Execute、MCP、Skill、Text2SQL、CodeAct）
- ✅ 完整 RAG 检索增强系统
- ✅ MCP 协议标准支持
- ✅ 多模型统一管理（通义千问、OpenAI、Claude、DeepSeek）
- ✅ 80+ 后端 API 接口
- ✅ 工程级代码质量

**技术架构：** 6 层分层架构（数据层、模型层、能力层、Agent决策层、对话层、用户层）

---

## 🎯 AI 协作核心原则

### 1. 语言使用规范

**必须使用中文：**
- ✅ 所有 AI 回复必须使用中文
- ✅ 所有文档编写必须使用中文
- ✅ 所有代码注释必须使用中文
- ✅ 变量/函数命名使用英文（符合编程规范）

### 2. 功能完成自检规范

**每次完成功能后必须自检：**
- [ ] 代码符合项目规范（命名、格式、中文注释）
- [ ] 核心功能正常工作，边界情况已处理
- [ ] 相关文档已更新（API 文档、数据库文档等）

**自检完成后说明：** `✅ 功能完成并已自检`

---

## 📚 设计文档索引

详细设计文档位于 `docs/` 目录，遇到问题请查阅相关文档：

| 文档 | 路径 | 查阅场景 |
|------|------|----------|
| **市场需求文档** | [docs/00-mrd.md](../docs/00-mrd.md) | 了解项目背景、目标用户、商业模式 |
| **产品需求文档** | [docs/01-prd.md](../docs/01-prd.md) | 查看功能清单、用户故事、页面结构 |
| **技术方案文档** | [docs/03-技术方案文档.md](../docs/03-技术方案文档.md) | 查看技术选型、系统架构、API 接口设计 |
| **技术选型文档** | [docs/技术选型.md](../docs/技术选型.md) | 了解技术栈选择原因和对比 |
| **代码架构文档** | [docs/代码架构.md](../docs/代码架构.md) | 查看目录结构、环境配置、启动命令 |
| **接口文档** | [docs/接口文档.md](../docs/接口文档.md) | 开发 API 时查阅接口定义、错误码 |
| **数据库文档** | [docs/数据库文档.md](../docs/数据库文档.md) | 查看数据库设计、表结构、索引策略 |
| **开发进度文档** | [docs/开发进度.md](../docs/开发进度.md) | 了解项目进度、功能完成情况 |
| **开发任务清单** | [docs/04-开发任务清单.md](../docs/04-开发任务清单.md) | 查看具体任务和实现状态 |
| **开发排期** | [docs/05-开发排期.md](../docs/05-开发排期.md) | 查看项目时间表和人员配置 |

**快速查找：**
- 需求理解 → MRD + PRD
- 架构设计 → 技术方案 + 代码架构
- 接口开发 → 接口文档
- 数据库变更 → 数据库文档
- 技术选型 → 技术选型文档

---

## 🔧 技术选型速查

### 前端技术栈

| 技术 | 版本 | 用途 |
|------|------|------|
| Vue 3 | ^3.4.21 | 渐进式框架，使用组合式 API |
| TypeScript | ^5.4.3 | 类型安全，禁止使用 any |
| Vite | ^5.2.8 | 构建工具 |
| Element Plus | ^2.7.0 | UI 组件库，按需引入 |
| Pinia | - | 状态管理，支持持久化 |
| Vue Router | 4+ | 路由管理，使用懒加载 |
| Axios | - | HTTP 客户端，统一封装 |

### 后端技术栈

| 技术 | 版本 | 用途 |
|------|------|------|
| Python | ^3.12 | 开发语言，遵循 PEP 8 |
| FastAPI | ^0.121.0 | Web 框架，使用异步 |
| LangChain | ^1.0.3 | AI 框架，标准 Chain 和 Agent |
| SQLModel | ^0.0.27 | ORM，基于 Pydantic |
| Redis | ^7.0.1 | 缓存，使用连接池 |
| MySQL | 8.0+ | 数据库，InnoDB 引擎，utf8mb4 |

### AI/ML 框架

| 框架/服务 | 用途 |
|-----------|------|
| LangChain | Agent 编排 |
| DashScope | 通义千问模型 |
| Anthropic | Claude 模型 |
| Tavily-Python | 网络搜索 |

---

## 📝 代码规范

### 文件命名

- Python 文件：`snake_case.py`
- Vue 组件：`PascalCase.vue`
- TypeScript 工具：`camelCase.ts`
- 配置文件：`kebab-case` 或点号分隔

### 命名约定

**前端：**
- 组件：PascalCase（如 `UserList`）
- 变量/函数：camelCase（如 `userName`）
- 常量：UPPER_SNAKE_CASE（如 `API_BASE_URL`）
- 类型/接口：PascalCase（如 `UserInfo`）

**后端：**
- 类：PascalCase（如 `UserService`）
- 函数/变量：snake_case（如 `get_user_by_id`）
- 常量：UPPER_SNAKE_CASE（如 `MAX_RETRIES`）

### 目录结构

**前端：** `src/api/`、`src/components/`、`src/pages/`、`src/stores/`、`src/router/`、`src/utils/`、`src/types/`、`src/constants/`

**后端：** `agentchat/api/`、`agentchat/core/`、`agentchat/database/`、`agentchat/services/`、`agentchat/tools/`、`agentchat/middleware/`、`agentchat/prompts/`、`agentchat/schema/`、`agentchat/utils/`

---

## 🌲 Git 规范

### 分支策略

```bash
main          # 生产环境（受保护）
├── develop   # 开发环境
    ├── feature/*   # 功能分支
    ├── bugfix/*    # 修复分支
    └── hotfix/*    # 紧急修复
```

### Commit 格式

**格式：** `<type>(<scope>): <subject>`

**类型：**
- `feat`: 新功能 | `fix`: 修复 Bug | `docs`: 文档更新
- `style`: 格式调整 | `refactor`: 重构 | `perf`: 性能优化
- `test`: 测试 | `chore`: 构建/工具链

**示例：**
- `feat(agent): 新增 React Agent 实现`
- `fix(auth): 修复 Token 过期时间计算错误`

---

## 📦 快速参考

### 本地开发

**后端启动：**
```bash
cd src/backend
python -m venv venv
source venv/bin/activate
pip install -r requirements.txt
python -m uvicorn agentchat.main:app --reload
```

**前端启动：**
```bash
cd src/frontend
npm install
npm run dev
```

**Docker 部署：**
```bash
docker-compose up -d
```

### 环境配置

- 使用 `.env.example` 作为模板
- 禁止提交 `.env` 文件
- 所有密钥从环境变量读取

### 常用命令

**Git：**
```bash
git checkout -b feature/xxx    # 创建功能分支
git merge --no-ff feature/xxx  # 合并分支
```

**数据库：**
```bash
python -m agentchat.database.init_db  # 初始化数据库
```

### 重要链接

- **GitHub**: https://github.com/your-org/OmniAgent
- **接口文档**: [docs/接口文档.md](../docs/接口文档.md)
- **代码架构**: [docs/代码架构.md](../docs/代码架构.md)
- **联系方式**: 微信 dtsola

---

## 📝 版本记录

- v1.0 (2026-05-14): 初始版本，简化版 AI 协作规范

---

**文档维护**: dtsola  
**最后更新**: 2026-05-14  
**文档类型**: AI 协作规范（每次 AI 会话自动加载）
