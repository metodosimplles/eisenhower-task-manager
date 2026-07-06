# 🚀 Deployment Guide

Guia para fazer deploy da aplicação em produção.

## Deploy no Railway

### Backend

1. Crie conta em [railway.app](https://railway.app)
2. Novo projeto
3. Selecione "GitHub"
4. Conecte seu repositório
5. Configure variáveis de ambiente
6. Deploy automático

### Frontend

1. Faça build: `npm run build`
2. Crie conta em [vercel.com](https://vercel.com)
3. Conecte seu repositório GitHub
4. Configure `VITE_API_URL` com URL do backend
5. Deploy automático

## Deploy no Heroku

### Backend

```bash
# Login
heroku login

# Create app
heroku create app-name

# Set environment variables
heroku config:set JWT_SECRET=your_secret_here
heroku config:set DATABASE_URL=postgresql://...

# Deploy
git push heroku main
```

## Variáveis de Ambiente Necessárias

### Backend
```
NODE_ENV=production
DATABASE_URL=postgresql://user:pass@host:port/db
JWT_SECRET=your_secret_key_here
API_PORT=3000
```

### Frontend
```
VITE_API_URL=https://your-api-url.com/api
```

## CI/CD com GitHub Actions

Ver `.github/workflows/` para configurações.

Documentation em desenvolvimento...
