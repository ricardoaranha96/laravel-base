Referência: https://dev.to/veevidify/docker-compose-up-your-entire-laravel-apache-mysql-development-environment-45ea

Primeiramente, deve-ser criar um grupo de usuários na máquina local para não conflitar com as permissões necessárias no Docker(este passo também evitará alguns problemas em projetos com a base de CakePHP):
sudo usermod -a -G www-data <nomeusuario>
Exemplo: sudo usermod -a -G www-data rikarudoaranha

Pode ser preciso relogar para que as permissões passem a funcionar.

Após subir o container, acessar o terminal do mesmo e rodar os comandosi abaixo para instalar as dependências:
$ composer install

Depois, rodar os comandos abaixo para iniciar o projeto:
$ php artisan key:generate
$ php artisan migrate
$ php artisan make:auth

Após os passos anteriores, exportar o banco e commitar o repositório para que todos os desenvolvedores utilizem as mesmas chaves