# Dify TOGAF Enterprise Architecture Documentation

This document describes the enterprise architecture views of the Dify platform based on TOGAF (The Open Group Architecture Framework) standards.

## Architecture Views Overview

Dify is an open-source platform for developing LLM applications. This document comprehensively describes its enterprise architecture from 5 dimensions:

### 1. Business Architecture View

**File**: `business-architecture-en.puml`

Describes the business capabilities, business processes, and business roles of the Dify platform, including:
- **Business Capabilities**: LLM application development platform, workflow builder, RAG pipeline, agent capabilities, model management
- **Business Processes**: Application creation process, dataset import process, conversation process, workflow execution process
- **Business Roles**: Developer, end user, administrator, workspace member

### 2. Application Architecture View

**File**: `application-architecture-en.puml`

Describes the application components, interfaces, and interaction relationships of the Dify platform, including:
- **Application Layer**: Frontend web application, backend API services, asynchronous task processing
- **Application Components**: Core business modules (Agent, Workflow, RAG, Model Runtime, Plugin)
- **Interface Relationships**: RESTful API, WebSocket, message queue

### 3. Data Architecture View

**File**: `data-architecture-en.puml`

Describes the data storage, data models, and data flows of the Dify platform, including:
- **Data Storage**: Relational database (PostgreSQL/MySQL), vector database (Weaviate), cache (Redis), object storage
- **Data Models**: Core entities such as Account, App, Dataset, Document, Workflow, Model, Provider
- **Data Flows**: Document import → indexing → retrieval, conversation data → log storage

### 4. Technology Architecture View

**File**: `technology-architecture-en.puml`

Describes the technology stack, infrastructure, and deployment architecture of the Dify platform, including:
- **Frontend Technology Stack**: Next.js 15, React 19, TypeScript, Tailwind CSS
- **Backend Technology Stack**: Python, Flask, SQLAlchemy, Celery, Gunicorn
- **Middleware**: PostgreSQL, Redis, Weaviate, Nginx
- **Deployment Architecture**: Docker containerization, Kubernetes support

### 5. Security Architecture View

**File**: `security-architecture-en.puml`

Describes the security controls, authentication and authorization, and data protection mechanisms of the Dify platform, including:
- **Authentication & Authorization**: OAuth 2.0, JWT Token, session management, API Key
- **Data Security**: Data encryption, credential management, SSRF protection proxy
- **Content Security**: Input/output content moderation, keyword filtering
- **Access Control**: Workspace isolation, application access control, role-based permissions
- **Security Monitoring**: Request logging, error tracking, OpenTelemetry tracing

## How to Use

### Viewing Diagrams

All architecture diagrams are written in PlantUML format and can be viewed in the following ways:

1. **Online Viewing**: Visit [PlantUML Online Editor](http://www.plantuml.com/plantuml/uml/) and paste the file content
2. **Local Tools**:
   - Install PlantUML: `brew install plantuml` (macOS) or `apt-get install plantuml` (Linux)
   - Generate images: `plantuml business-architecture-en.puml`
3. **IDE Plugins**: Install PlantUML plugins in IDEs like VS Code, IntelliJ IDEA, etc.

### Architecture View Relationships

The following relationships exist between architecture views:

```
Business Architecture View
    ↓ (drives)
Application Architecture View
    ↓ (implements)
Technology Architecture View
    ↓ (supports)
Data Architecture View
    ↓ (protects)
Security Architecture View
```

- **Business Architecture** defines "What" to do
- **Application Architecture** defines "How to organize" (How - Application)
- **Technology Architecture** defines "How to implement" (How - Technology)
- **Data Architecture** defines "How to manage data" (How - Data)
- **Security Architecture** runs through all layers, defining "How to protect" (How - Security)

## Architecture Principles

The Dify platform follows these architecture principles:

1. **Domain-Driven Design (DDD)**: Backend adopts DDD architecture with clear domain boundaries and layering
2. **Clean Architecture**: Frontend and backend separation, separation of concerns
3. **Microservices**: Supports containerized deployment, scalable distributed architecture
4. **API-First**: All features provide corresponding API interfaces
5. **Security First**: Multi-layered security control mechanisms

## Update History

- 2024-12: Initial version, generated based on current Dify project architecture

## Reference Resources

- [TOGAF Standard](https://www.opengroup.org/togaf)
- [PlantUML Documentation](https://plantuml.com/)
- [Dify Project Documentation](https://docs.dify.ai)

