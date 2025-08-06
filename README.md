# 📦 docker-laravel

Este projeto é uma aplicação de base para criação dos containers de uma aplicação laravel.  
Siga as instruções abaixo para executar e iniciar a aplicação localmente.

---

## 🚀 Como Executar

1. Faça uma cópia do arquivo .env.example para .env e defina o USER e o UID:

Exemplo:

```bash
#Define UID USER LARAVEL
USER = laravel
UID = 1001
```
*** Não esqueça de criar o diretório /src ***

2. Execute o build e o Up dos containers:
```bash
docker compose build && docker compose up -d
```

3. No diretório da aplicação /src, então, execute o comando:

```bash
docker compose exec app composer create-project laravel/laravel .
```

4. Acesse o localhost
```bash
http://localhost:8000
```

5. Após configurar o arquivo .env do projeto laravel em /src com a definição do banco de dados, execute as migrations:

Exemplo:

```bash
DB_CONNECTION=mysql
DB_PORT=3306
DB_DATABASE=laravel
DB_USERNAME=laravel
DB_HOST=db
DB_PASSWORD=secret
```

Em seguida, rode as migrations:

```bash
docker compose exec app php artisan migrate
```

6. Para destruir os containers e volumes por completo:
```bash
docker compose down --rmi all --volumes --remove-orphans
```

