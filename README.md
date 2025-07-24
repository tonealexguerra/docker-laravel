# 📦 docker-laravel

Este projeto é uma aplicação de base para criação dos containers de uma aplicação laravel.  
Siga as instruções abaixo para executar e iniciar a aplicação localmente.

---

## 🚀 Como Executar

1. Faça uma cópia do arquivo .env.example para .env e defina o USER e o UID:

2. No diretório da aplicação /src, execute o comando:

```bash
docker compose create-project laravel/laravel .
```

3. Execute o build e o Up dos containers:
```bash
docker compose build && docker compose up -d
```

4. Acesse o localhost
```bash
http://localhost:8000
```