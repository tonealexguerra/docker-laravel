FROM php:8.4-fpm

# Argumentos para usuário
ARG user
ARG uid

# Dependências e extensões PHP
RUN apt-get update && apt-get install -y \
    git curl zip unzip libpng-dev libonig-dev libxml2-dev libzip-dev \
    && docker-php-ext-install pdo_mysql mbstring exif pcntl bcmath gd sockets zip \
    && apt-get clean && rm -rf /var/lib/apt/lists/*

# Criar usuário com UID vindo do host
RUN groupadd -g ${uid} ${user} \
    && useradd -u ${uid} -g ${user} -m -s /bin/bash ${user}

# Instala Composer
COPY --from=composer:latest /usr/bin/composer /usr/bin/composer

# Define diretório de trabalho e permissões
WORKDIR /var/www
RUN chown -R ${user}:${user} /var/www

# Troca para o usuário criado
USER ${user}

# PATH do Composer
ENV PATH="/home/${user}/.composer/vendor/bin:${PATH}"

CMD ["php-fpm"]
