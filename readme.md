Projeto em Laravel

Inclui:

- Login de autenticação do laravel
- Controle de acesso (ACL)
- Auditoria das operações

<<< Instalação  <<<

git clone https://github.com/hercolysm/laravel_acl.git
cd laravel_acl

# criar arquivo de configurações
cp .env.example .env

# configurar banco mysql
vim .env
DB_CONNECTION=mysql
DB_HOST=192.168.1.11
DB_PORT=3306
DB_DATABASE=nome_do_banco
DB_USERNAME=nome_do_usuario
DB_PASSWORD=nome_do_usuario123@

# instalar composer (global)
(buscar arquivo atualizado no link 'https://getcomposer.org/download/')
php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"
php -r "if (hash_file('SHA384', 'composer-setup.php') === '669656bab3166a7aff8a7506b8cb2d1c292f042046c5a994c43155c0be6190fa0355160742ab2e1c88d40d5be660b410') { echo 'Installer verified'; } else { echo 'Installer corrupt'; unlink('composer-setup.php'); } echo PHP_EOL;"
php composer-setup.php --install-dir=/usr/local/bin --filename=composer
php -r "unlink('composer-setup.php');"

composer install (corrigir dependências)

php artisan key:generate

chmod 777 -R storage/framework/sessions/
chmod 777 -R storage/framework/views/
chmod 777 -R storage/logs/

php artisan serve --host=127.0.0.1 --port=80

# criar BD mysql
mysql> create database nome_do_banco;

# migrar BD
php artisan migrate:install
php artisan migrate:status
php artisan migrate

# semear BD
php artisan db:seed

# acessar no navegador
http://127.0.0.1
login: admin@admin
senha: 1234

Aproveite isso! ;)
