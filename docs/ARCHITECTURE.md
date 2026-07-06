# 🏗️ Architecture Guide

Documentação em desenvolvimento...

## Visão Geral

A arquitetura segue padrões MVC + Service Layer:

```
Controller → Service → Repository → Database
       ↓
     Request Validation
```

## Backend Architecture

### Layers

1. **Controllers** - Lidam com requisições HTTP
2. **Services** - Lógica de negócio
3. **Repositories** - Acesso ao banco de dados
4. **Models/Entities** - Estrutura de dados
5. **Middleware** - Autenticação, validação, erro handling

### Directory Structure

```
src/
├── entities/       → Database models
├── routes/         → Route definitions
├── controllers/    → Request handlers
├── services/       → Business logic
├── middleware/     → Request interceptors
├── config/         → Configuration
└── utils/          → Helper functions
```

## Frontend Architecture

### Layers

1. **Pages** - Páginas da aplicação
2. **Components** - Componentes reutilizáveis
3. **Hooks** - Custom React hooks
4. **Store** - State management (Zustand)
5. **Services** - API communication
6. **Types** - TypeScript interfaces

### State Management

Usamos Zustand para gerenciar estado:

- `authStore` - Autenticação e usuário
- `taskStore` - Tarefas e backlog
- `uiStore` - UI state (modals, temas, etc)

## Data Flow

```
User Input
    ↓
Component
    ↓
Zustand Store / API Service
    ↓
Backend API
    ↓
Database
    ↓
Response
    ↓
Update Store
    ↓
Re-render Component
```

Documentation em desenvolvimento...
