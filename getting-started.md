##Getting started

O Kep Framework está em sua primeira versão BETA, criado para iniciantes se familiarizam com frameworks profissionais, como o Laravel, trazendo simplicidade para a criação de APIs em PHP, com uma boa performance e agilidade.

Conta com sistemas de Rotas, Controles e modelos e a facilidade de conexão com o banco de dados MySQL.

##Instalação

Primeiro, faça o download do Kep Installer usando o [Composer](https://getcomposer.org/):

	composer global require "getkep/installer"

Certifique-se de colocar o diretório `$HOME/.composer/vendor/bin` (Ou o diretório que foi instalado em seu OS) no seu `$PATH` para o executável do `kep`.

Quando instalado, o novo comando `kep new` irá criar uma instalação do Kep fresquinha no diretório que você especificar. Exemplo, `kep new api` vai criar um diretório chamado api, contendo uma instalação fresquinha, com todas as dependências do Kep instaladas:

    kep new api 

##Configuração

### Apache

Para o funcionamento correto da API em um servidor Apache, precisamos criar urls amigaveis e deixar o Kep cuidar do assunto.

	RewriteEngine On
	RewriteCond %{REQUEST_FILENAME} !-f
	RewriteCond %{REQUEST_FILENAME} !-d
	RewriteRule .index.php [L]

### Configuração de arquivos

Fique a vontade para poder renomear o diretório do Kep, de `v1` para outra informação correspondente a sua API, fique ciente de alterar no arquivo `config.php` o nome do diretório.

##Routes

Para o configuramento de rotas no arquivo index.php, leia mais sobre [Routes](/#/docs/routing).

##Controller

Para criar os controllers, leia mais sobre [Controller](/#/docs/controller).

##Model

Para a criar o model e interagir com o controller, leia mais sobre [Model](/#/docs/model).

##Views

Utilizar o AngularJS como view para consumir a nossa API, veja alguns detalhes em [View AngularJS](/#/docs/angularjs)

##Seeds

Para criar as suas proprias classes e reutilizar de forma eficiente nos controllers, leia mais sobre [Seeds](/#/docs/seeds).
