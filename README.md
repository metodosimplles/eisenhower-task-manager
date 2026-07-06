# 📋 Eisenhower Task Manager

Uma ferramenta moderna de controle de tarefas baseada na **Matriz de Eisenhower**, ajudando você a priorizar o que realmente importa.

![Version](https://img.shields.io/badge/version-0.1.0-blue)
![Status](https://img.shields.io/badge/status-in%20development-yellow)
![License](https://img.shields.io/badge/license-MIT-green)

## 🎯 Visão Geral

A Matriz de Eisenhower divide suas tarefas em 4 quadrantes:

```
┌─────────────────────────────────────────┐
│           IMPORTANTE                    │
│  ┌──────────────┬──────────────┐        │
│  │  Q1: Fazer   │  Q2: Planejar│        │
│  │   Agora      │   (Importante)        │
│  ├──────────────┼──────────────┤ URGENTE│
│  │  Q3: Delegar │  Q4: Eliminar│        │
│  │  (Urgente)   │  (Nem Urgente│        │
│  └──────────────┴──────────────┘        │
│                                         │
│        NÃO IMPORTANTE                   │
└─────────────────────────────────────────┘
```

## ✨ Funcionalidades

- ✅ Backlog centralizado
- ✅ Matriz de Eisenhower interativa
- ✅ Drag & Drop entre quadrantes
- ✅ Dashboard com estatísticas
- ✅ Autenticação segura (JWT)
- ✅ Tags e categorias
- ✅ Filtros avançados
- ✅ Responsivo (Mobile/Desktop)
- 🔄 Relatórios e exportação (em breve)
- 🔄 Notificações e lembretes (em breve)

## 🚀 Tech Stack

### Frontend
- **React 18** com TypeScript
- **Vite** - Build tool rápido
- **Tailwind CSS** - Styling moderno
- **React Router** - Navegação
- **Axios** - HTTP Client
- **Zustand** - State Management
- **React Beautiful DnD** - Drag & Drop

### Backend
- **Node.js** com Express
- **TypeScript** - Type safety
- **PostgreSQL** - Database
- **TypeORM** - ORM
- **JWT** - Autenticação
- **Bcrypt** - Password hashing
- **Zod** - Validação

### DevOps
- **Docker** - Containerização
- **GitHub Actions** - CI/CD
- **Jest** - Testing

## 📁 Estrutura do Projeto

Veja [PLANEJAMENTO.md](./PLANEJAMENTO.md) para estrutura completa.

## 🛠️ Instalação Rápida

### Pré-requisitos
- Node.js 18+
- PostgreSQL 14+
- Docker (opcional)

### Com Docker (Recomendado)
```bash
git clone https://github.com/metodosimplles/eisenhower-task-manager.git
cd eisenhower-task-manager
docker-compose up -d
```

### Setup Manual

**Backend:**
```bash
cd backend
npm install
cp .env.example .env
npm run dev
```

**Frontend:**
```bash
cd frontend
npm install
npm run dev
```

A aplicação estará disponível em `http://localhost:5173`

## 📖 Documentação

- [Planejamento Detalhado](./PLANEJAMENTO.md)
- [API Documentation](./docs/API.md) (em desenvolvimento)
- [Architecture Guide](./docs/ARCHITECTURE.md) (em desenvolvimento)
- [User Guide](./docs/USER_GUIDE.md) (em desenvolvimento)
- [Development Guide](./docs/DEVELOPMENT.md) (em desenvolvimento)

## 🗺️ Roadmap

### v0.1.0 (MVP) - Fase 1-3
- [ ] Backend API completa
- [ ] Frontend da Matriz
- [ ] Autenticação
- [ ] Backlog funcional

### v1.0.0 - Fase 4-5
- [ ] Dashboard completo
- [ ] Testes
- [ ] Deploy
- [ ] Documentação completa

### v2.0.0
- [ ] Relatórios avançados
- [ ] Exportação (PDF/CSV)
- [ ] Notificações
- [ ] Compartilhamento de tarefas

## 🤝 Contribuindo

Contribuições são bem-vindas! Para grandes mudanças, abra uma issue primeiro.

## 📄 Licença

MIT License - veja o arquivo LICENSE para detalhes.

## 👨‍💻 Autor

[metodosimplles](https://github.com/metodosimplles)

---

**Desenvolvido com ❤️ para ajudar você a priorizar o que realmente importa.**
