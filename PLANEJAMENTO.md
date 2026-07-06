# 📋 PLANEJAMENTO - Ferramenta de Controle de Tarefas (Matriz de Eisenhower)

## 🎯 Visão Geral do Projeto

Uma aplicação web moderna e responsiva para organizar tarefas usando a **Matriz de Eisenhower**, que classifica atividades em 4 quadrantes baseado em **urgência** e **importância**.

### Os 4 Quadrantes:
1. **Q1 (Urgente + Importante)**: ⚡ **FAZER AGORA** - Crises, deadlines
2. **Q2 (Importante + Não Urgente)**: 📅 **AGENDAR** - Desenvolvimento, planejamento
3. **Q3 (Urgente + Não Importante)**: 🔄 **DELEGAR** - Interrupções, reuniões
4. **Q4 (Não Urgente + Não Importante)**: 🗑️ **ELIMINAR** - Distrações

---

## 🏗️ Tech Stack (Viável & Moderno)

### **Frontend**
```
✅ React 18 + TypeScript
✅ Vite (Build super rápido)
✅ Tailwind CSS (Styling elegante)
✅ React Router v6
✅ Zustand (State management leve)
✅ Axios (HTTP Client)
✅ React Beautiful DnD (Drag & Drop)
```

### **Backend**
```
✅ Node.js + Express.js
✅ TypeScript (Type safety)
✅ PostgreSQL 14+ (Database robusto)
✅ TypeORM (ORM para TS)
✅ JWT (Autenticação segura)
✅ Bcrypt (Password hashing)
✅ Zod (Validação de schemas)
```

### **DevOps & Tools**
```
✅ Docker & Docker Compose
✅ GitHub Actions (CI/CD)
✅ Jest (Testing)
✅ ESLint & Prettier (Code quality)
✅ Railway/Vercel (Deploy)
```

---

## 📊 Estrutura de Dados

### **User**
```typescript
{
  id: UUID (PK),
  email: String (unique),
  password: String (hashed),
  name: String,
  createdAt: DateTime,
  updatedAt: DateTime
}
```

### **Task**
```typescript
{
  id: UUID (PK),
  userId: UUID (FK -> User),
  title: String,
  description: Text,
  quadrant: Number (1-4) | null (backlog),
  priority: 'low' | 'medium' | 'high',
  status: 'pending' | 'completed' | 'cancelled',
  category: String,
  tags: String[],
  dueDate: DateTime,
  createdAt: DateTime,
  updatedAt: DateTime,
  completedAt: DateTime (nullable),
  position: Integer (order in quadrant)
}
```

### **Category**
```typescript
{
  id: UUID (PK),
  userId: UUID (FK -> User),
  name: String,
  color: String (hex),
  createdAt: DateTime
}
```

---

## 🗂️ Estrutura de Pastas

```
eisenhower-task-manager/
│
├── backend/
│   ├── src/
│   │   ├── entities/
│   │   │   ├── User.ts
│   │   │   ├── Task.ts
│   │   │   └── Category.ts
│   │   ├── routes/
│   │   │   ├── auth.routes.ts
│   │   │   ├── tasks.routes.ts
│   │   │   └── categories.routes.ts
│   │   ├── controllers/
│   │   │   ├── authController.ts
│   │   │   ├── taskController.ts
│   │   │   └── categoryController.ts
│   │   ├── services/
│   │   │   ├── authService.ts
│   │   │   ├── taskService.ts
│   │   │   └── categoryService.ts
│   │   ├── middleware/
│   │   │   ├── authMiddleware.ts
│   │   │   ├── errorHandler.ts
│   │   │   └── validation.ts
│   │   ├── config/
│   │   │   ├── database.ts
│   │   │   └── env.ts
│   │   ├── utils/
│   │   │   ├── jwt.ts
│   │   │   └── errors.ts
│   │   ├── app.ts
│   │   └── server.ts
│   ├── migrations/
│   ├── .env.example
│   ├── Dockerfile
│   ├── package.json
│   ├── tsconfig.json
│   └── .dockerignore
│
├── frontend/
│   ├── src/
│   │   ├── components/
│   │   │   ├── Common/
│   │   │   │   ├── Header.tsx
│   │   │   │   ├── Sidebar.tsx
│   │   │   │   ├── Button.tsx
│   │   │   │   └── Modal.tsx
│   │   │   ├── Matrix/
│   │   │   │   ├── Matrix.tsx
│   │   │   │   ├── Quadrant.tsx
│   │   │   │   ├── TaskCard.tsx
│   │   │   │   └── TaskForm.tsx
│   │   │   ├── Backlog/
│   │   │   │   ├── BacklogList.tsx
│   │   │   │   ├── BacklogTask.tsx
│   │   │   │   └── AddTaskForm.tsx
│   │   │   └── Dashboard/
│   │   │       ├── Dashboard.tsx
│   │   │       ├── Stats.tsx
│   │   │       └── QuickActions.tsx
│   │   ├── pages/
│   │   │   ├── Login.tsx
│   │   │   ├── Register.tsx
│   │   │   ├── Home.tsx
│   │   │   ├── Matrix.tsx
│   │   │   ├── Backlog.tsx
│   │   │   └── NotFound.tsx
│   │   ├── services/
│   │   │   ├── api.ts
│   │   │   ├── auth.ts
│   │   │   └── tasks.ts
│   │   ├── store/
│   │   │   ├── authStore.ts
│   │   │   ├── taskStore.ts
│   │   │   └── uiStore.ts
│   │   ├── hooks/
│   │   │   ├── useAuth.ts
│   │   │   ├── useTasks.ts
│   │   │   └── useLocalStorage.ts
│   │   ├── styles/
│   │   │   ├── globals.css
│   │   │   └── tailwind.config.ts
│   │   ├── types/
│   │   │   └── index.ts
│   │   ├── App.tsx
│   │   └── main.tsx
│   ├── public/
│   ├── vite.config.ts
│   ├── tailwind.config.ts
│   ├── package.json
│   ├── tsconfig.json
│   ├── index.html
│   └── .env.example
│
├── docs/
│   ├── API.md
│   ├── ARCHITECTURE.md
│   ├── DEVELOPMENT.md
│   ├── USER_GUIDE.md
│   └── DEPLOYMENT.md
│
├── .github/
│   └── workflows/
│       ├── ci.yml
│       └── deploy.yml
│
├── docker-compose.yml
├── .gitignore
├── LICENSE
└── PLANEJAMENTO.md
```

---

## 🚀 Fases de Desenvolvimento

### **FASE 1: Setup & Inicialização (2 dias)**
- [x] Criar repositório
- [ ] Setup backend (Express + TypeScript + PostgreSQL)
- [ ] Setup frontend (React + Vite + TypeScript)
- [ ] Docker & docker-compose
- [ ] Documentação inicial

### **FASE 2: Backend - Core API (4-5 dias)**

#### 2.1 - Autenticação
- [ ] Models (User)
- [ ] Endpoints: POST /auth/register
- [ ] Endpoints: POST /auth/login
- [ ] JWT middleware
- [ ] Password hashing (bcrypt)

#### 2.2 - Tarefas (CRUD)
- [ ] Models (Task, Category)
- [ ] Endpoints: GET /tasks
- [ ] Endpoints: POST /tasks
- [ ] Endpoints: PUT /tasks/:id
- [ ] Endpoints: DELETE /tasks/:id
- [ ] Endpoints: PATCH /tasks/:id/quadrant (mover)
- [ ] Endpoints: PATCH /tasks/:id/status (marcar completo)

#### 2.3 - Backlog
- [ ] Endpoints: GET /backlog
- [ ] Endpoints: POST /backlog (criar tarefa)
- [ ] Endpoints: DELETE /backlog/:id (mover para matrix)

#### 2.4 - Relatórios
- [ ] Endpoints: GET /dashboard/stats
- [ ] Endpoints: GET /tasks/by-quadrant
- [ ] Endpoints: GET /tasks/by-status

#### 2.5 - Validação & Tratamento de Erros
- [ ] Zod schemas
- [ ] Error middleware
- [ ] Request validation

### **FASE 3: Frontend - UI Principal (4-6 dias)**

#### 3.1 - Setup & Componentes Base
- [ ] Vite + React config
- [ ] Tailwind setup
- [ ] Componentes reutilizáveis (Button, Card, Modal)
- [ ] Layouts base

#### 3.2 - Autenticação
- [ ] Página Login
- [ ] Página Register
- [ ] Protected Routes
- [ ] Token management

#### 3.3 - Matriz de Eisenhower
- [ ] Layout 2x2
- [ ] 4 Quadrantes (Q1, Q2, Q3, Q4)
- [ ] Task Cards
- [ ] Drag & Drop entre quadrantes
- [ ] Modal de edição

#### 3.4 - Backlog
- [ ] Lista de tarefas
- [ ] Adicionar nova tarefa
- [ ] Editar tarefa
- [ ] Mover para Matriz
- [ ] Deletar tarefa

#### 3.5 - Dashboard
- [ ] Cards com estatísticas
- [ ] Gráfico de distribuição
- [ ] Tasks pendentes
- [ ] Atalhos rápidos

#### 3.6 - Features
- [ ] Filtros (por status, prioridade, categoria)
- [ ] Busca
- [ ] Temas (claro/escuro)
- [ ] Responsividade

### **FASE 4: Integração & Testes (3-4 dias)**

- [ ] Conectar frontend com backend
- [ ] Testes unitários (Jest)
- [ ] Testes de integração
- [ ] Testes E2E (Cypress/Playwright)
- [ ] Bug fixes

### **FASE 5: Deploy & Otimização (2-3 dias)**

- [ ] CI/CD (GitHub Actions)
- [ ] Deploy backend (Railway/Heroku)
- [ ] Deploy frontend (Vercel/Netlify)
- [ ] Documentação final
- [ ] Monitoramento

---

## 📋 API Endpoints

### Authentication
```
POST   /api/auth/register        - Criar conta
POST   /api/auth/login           - Fazer login
POST   /api/auth/refresh         - Renovar token
```

### Tasks
```
GET    /api/tasks                - Listar todas
GET    /api/tasks/:id            - Detalhes
POST   /api/tasks                - Criar tarefa
PUT    /api/tasks/:id            - Editar
DELETE /api/tasks/:id            - Deletar
PATCH  /api/tasks/:id/quadrant   - Mover para quadrante
PATCH  /api/tasks/:id/status     - Marcar completo/incompleto
```

### Backlog
```
GET    /api/backlog              - Listar backlog
POST   /api/backlog              - Criar no backlog
DELETE /api/backlog/:id          - Remover do backlog
```

### Dashboard
```
GET    /api/dashboard/stats      - Estatísticas gerais
GET    /api/dashboard/by-quadrant - Count por quadrante
GET    /api/dashboard/by-priority - Count por prioridade
```

### Categories
```
GET    /api/categories           - Listar categorias
POST   /api/categories           - Criar categoria
PUT    /api/categories/:id       - Editar
DELETE /api/categories/:id       - Deletar
```

---

## 🎨 Fluxo de Usuário

```
┌─────────────┐
│    Login    │
└──────┬──────┘
       │
       ▼
┌──────────────┐
│  Dashboard   │ (visão geral)
└──────┬───────┘
       │
       ├─────────────────────────┐
       │                         │
       ▼                         ▼
   ┌────────┐            ┌──────────┐
   │ Backlog│            │  Matriz  │
   └────┬───┘            └──────────┘
        │
        │ Criar tarefa
        │
        ▼
   ┌─────────────────┐
   │ Modal: Add Task │
   │ - Título        │
   │ - Descrição     │
   │ - Categoria     │
   │ - Prioridade    │
   └────────┬────────┘
            │
            ▼
   ┌──────────────────┐
   │ Salvar no Backlog│
   └────────┬─────────┘
            │
            │ Classificar
            │
            ▼
   ┌────────────────────────────┐
   │ Mover para Quadrante:      │
   │ Q1 / Q2 / Q3 / Q4          │
   │ (via Drag & Drop ou Modal) │
   └────────┬───────────────────┘
            │
            ▼
   ┌──────────────────┐
   │ Executar/Gerenciar│
   │ - Marcar completo │
   │ - Editar          │
   │ - Deletar         │
   └──────────────────┘
```

---

## ✅ Checklist MVP

### Backend
- [ ] Express servidor rodando
- [ ] PostgreSQL conectado
- [ ] JWT autenticação
- [ ] CRUD tarefas básico
- [ ] Validação com Zod
- [ ] Error handling
- [ ] Testes unitários

### Frontend
- [ ] React + Vite rodando
- [ ] Tailwind CSS configurado
- [ ] Login/Register funcional
- [ ] Matriz 2x2 visual
- [ ] Backlog funcional
- [ ] Drag & Drop básico
- [ ] Responsividade mobile

### DevOps
- [ ] Docker files
- [ ] docker-compose
- [ ] GitHub Actions
- [ ] Variáveis de ambiente

---

## 📅 Timeline Realista

| Fase | Duração | 
|------|----------|
| Setup & Init | 2 dias |
| Backend | 4-5 dias |
| Frontend | 4-6 dias |
| Integração & Testes | 3-4 dias |
| Deploy & Docs | 2-3 dias |
| **TOTAL** | **15-20 dias** |

---

## 🔧 Comandos Iniciais

```bash
# Clone
git clone https://github.com/metodosimplles/eisenhower-task-manager.git
cd eisenhower-task-manager

# Setup com Docker (recomendado)
docker-compose up -d

# Ou manual:

# Backend
cd backend
npm install
cp .env.example .env
npm run dev

# Frontend (em outro terminal)
cd frontend
npm install
npm run dev
```

---

## 📞 Próximos Passos

1. ✅ **Planejamento criado e aprovado**
2. 🚀 **Começar Fase 1: Setup inicial**
3. 🔨 **Estruturar projeto com Docker**
4. 🗄️ **Configurar banco de dados**
5. 📡 **Iniciar API backend**

---

**Pronto para começar? 🚀**
