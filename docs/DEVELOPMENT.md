# 👨‍💻 Development Guide

Guia para desenvolvedores contribuirem no projeto.

## Setup do Ambiente

### Pré-requisitos

- Node.js 18+
- PostgreSQL 14+
- Docker (opcional mas recomendado)
- Git

### Instalação Local

#### Backend

```bash
cd backend
npm install
cp .env.example .env

# Configure o arquivo .env com suas credenciais do banco

# Execute as migrations
npm run migrate

# Inicie o servidor
npm run dev
```

#### Frontend

```bash
cd frontend
npm install
cp .env.example .env

# Inicie o dev server
npm run dev
```

### Com Docker

```bash
docker-compose up -d
```

## Scripts Disponíveis

### Backend

```bash
npm run dev          # Start dev server
npm run build        # Build para produção
npm run start        # Start production server
npm run migrate      # Run database migrations
npm run test         # Run tests
npm run lint         # Lint code
npm run format       # Format code
```

### Frontend

```bash
npm run dev          # Start dev server
npm run build        # Build para produção
npm run preview      # Preview production build
npm run test         # Run tests
npm run lint         # Lint code
npm run format       # Format code
```

## Convenções de Código

### Naming

- **Files**: `camelCase.ts` or `PascalCase.tsx`
- **Variables/Functions**: `camelCase`
- **Classes/Components**: `PascalCase`
- **Constants**: `UPPER_SNAKE_CASE`

### TypeScript

- Sempre use tipos explícitos
- Evite `any` - use tipos genéricos
- Interface para contracts públicos
- Type para types utilitários

### Git

#### Commits

```
<type>(<scope>): <subject>

<body>

<footer>
```

**Types**: feat, fix, docs, style, refactor, test, chore

**Examples**:
```
feat(auth): add JWT authentication
fix(tasks): correct quadrant assignment logic
docs(api): update endpoint documentation
```

#### Branches

```
feature/description
fix/description
docs/description
refactor/description
```

## Fluxo de Desenvolvimento

1. Crie uma branch: `git checkout -b feature/minha-feature`
2. Faça suas alterações
3. Commit: `git commit -m "feat(module): description"`
4. Push: `git push origin feature/minha-feature`
5. Abra um Pull Request
6. Aguarde review
7. Merge após aprovação

## Testing

### Backend

```bash
# Rodando testes
npm run test

# Com coverage
npm run test:coverage

# Watch mode
npm run test:watch
```

### Frontend

```bash
# Rodando testes
npm run test

# Com coverage
npm run test:coverage

# Watch mode
npm run test:watch
```

## Troubleshooting

### Banco de dados não conecta

1. Verifique se PostgreSQL está rodando
2. Confira credenciais no `.env`
3. Teste a conexão: `psql postgresql://user:pass@localhost:5432/db`

### Frontend não conecta na API

1. Verifique se backend está rodando (porta 3000)
2. Confira `VITE_API_URL` no `.env`
3. Check browser console para erros

### Problemas com Docker

```bash
# Limpar containers
docker-compose down

# Remover volumes
docker-compose down -v

# Rebuild
docker-compose up --build
```

## Documentação em desenvolvimento...
