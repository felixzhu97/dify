# Dify TOGAF 企业架构文档

本文档基于TOGAF（The Open Group Architecture Framework）标准，描述了Dify平台的企业架构视图。

## 架构视图概览

Dify是一个开源的LLM应用开发平台，本文档从5个维度全面描述其企业架构：

### 1. 业务架构视图 (Business Architecture)

**文件**: `business-architecture.puml`

描述Dify平台的业务能力、业务流程和业务角色，包括：
- **业务能力**：LLM应用开发平台、工作流构建、RAG管道、Agent能力、模型管理
- **业务流程**：应用创建流程、数据集导入流程、对话流程、工作流执行流程
- **业务角色**：开发者、终端用户、管理员、工作空间成员

### 2. 应用架构视图 (Application Architecture)

**文件**: `application-architecture.puml`

描述Dify平台的应用组件、接口和交互关系，包括：
- **应用层**：前端Web应用、后端API服务、异步任务处理
- **应用组件**：核心业务模块（Agent、Workflow、RAG、Model Runtime、Plugin）
- **接口关系**：RESTful API、WebSocket、消息队列

### 3. 数据架构视图 (Data Architecture)

**文件**: `data-architecture.puml`

描述Dify平台的数据存储、数据模型和数据流，包括：
- **数据存储**：关系数据库（PostgreSQL/MySQL）、向量数据库（Weaviate）、缓存（Redis）、对象存储
- **数据模型**：Account、App、Dataset、Document、Workflow、Model、Provider等核心实体
- **数据流**：文档导入→索引→检索、对话数据→日志存储

### 4. 技术架构视图 (Technology Architecture)

**文件**: `technology-architecture.puml`

描述Dify平台的技术栈、基础设施和部署架构，包括：
- **前端技术栈**：Next.js 15、React 19、TypeScript、Tailwind CSS
- **后端技术栈**：Python、Flask、SQLAlchemy、Celery、Gunicorn
- **中间件**：PostgreSQL、Redis、Weaviate、Nginx
- **部署架构**：Docker容器化、Kubernetes支持

### 5. 安全架构视图 (Security Architecture)

**文件**: `security-architecture.puml`

描述Dify平台的安全控制、认证授权和数据保护机制，包括：
- **认证授权**：OAuth 2.0、JWT Token、Session管理、API Key
- **数据安全**：数据加密、凭证管理、SSRF防护代理
- **内容安全**：输入/输出内容审核、关键词过滤
- **访问控制**：工作空间隔离、应用访问控制、角色权限管理
- **安全监控**：请求日志、错误追踪、OpenTelemetry追踪

## 如何使用

### 查看图表

所有架构图使用PlantUML格式编写，可以通过以下方式查看：

1. **在线查看**：访问 [PlantUML在线编辑器](http://www.plantuml.com/plantuml/uml/) 并粘贴文件内容
2. **本地工具**：
   - 安装PlantUML：`brew install plantuml` (macOS) 或 `apt-get install plantuml` (Linux)
   - 生成图片：`plantuml business-architecture.puml`
3. **IDE插件**：在VS Code、IntelliJ IDEA等IDE中安装PlantUML插件

### 架构视图关系

各架构视图之间存在以下关系：

```
业务架构视图
    ↓ (驱动)
应用架构视图
    ↓ (实现)
技术架构视图
    ↓ (支撑)
数据架构视图
    ↓ (保护)
安全架构视图
```

- **业务架构**定义了"做什么"（What）
- **应用架构**定义了"如何组织"（How - Application）
- **技术架构**定义了"如何实现"（How - Technology）
- **数据架构**定义了"数据如何管理"（How - Data）
- **安全架构**贯穿所有层面，定义了"如何保护"（How - Security）

## 架构原则

Dify平台遵循以下架构原则：

1. **领域驱动设计（DDD）**：后端采用DDD架构，清晰的领域边界和分层
2. **整洁架构**：前后端分离，关注点分离
3. **微服务化**：支持容器化部署，可扩展的分布式架构
4. **API优先**：所有功能提供对应的API接口
5. **安全第一**：多层次的安全控制机制

## 更新历史

- 2024-12：初始版本，基于Dify项目当前架构生成

## 参考资源

- [TOGAF标准](https://www.opengroup.org/togaf)
- [PlantUML文档](https://plantuml.com/)
- [Dify项目文档](https://docs.dify.ai)

