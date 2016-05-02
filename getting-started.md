##Getting started

O Kep Framework está em sua primeira versão BETA, criado para iniciantes se familiarizam com frameworks profissionais, como o Laravel, trazendo simplicidade para a criação de APIs em PHP, com uma boa performance e agilidade.

Conta com sistemas de Rotas, Controles e modelos e a facilidade de conexão com o banco de dados MySQL.

##Instalação

Instalação pelo composer, certifique-se de ter [Composer](https://getcomposer.org/) instalado em sua máquina.

	composer require getkep/kep v0.4.0

Acompanhe as versões em nosso [repositório](https://github.com/getkep/Kep/releases) no Github e lembre sempre em instalar a última versão.

##Configuração

Depois da instalação do Kep com composer em uma pasta, precisamos criar uma nova pasta com qualquer nome(Certifique-se de adicionar este nome na configuração do Kep).

Abra a pasta e crie mais 3, com os nomes controllers, models e seeds. a arquitetura de nossa aplicação fica assim:

	api/
       ├─ v1/
       │    ├─ controllers/
       │    ├─ models/
       │    └─ seeds/
       └─ vendor/

Para o Kep, identificar a pasta e efetuar conexão com o banco de dados, precisamos criar o arquivo de configuração na pasta raiz do projeto (Antes da pasta vendor), com o nome config.php.

A estrutura do arquivo a seguir.

	config.php
	vendor/

	class configuration
    {
        public function config()
        {
            return [
                'directory' => "v1",
                'connections' => [
                    'driver' => 'mysqli',
                    'host' => 'localhost',
                    'database' => 'Data',
                    'username' => 'root',
                    'password' => 'password',
                ],
                'authentication' => [
                    'mysql' => [
                        'activate' => true,
                        'table' => 'Tabela',
                        'column' => 'Coluna',
                    ],
                ],
            ];
        }
    }

Você pode configurar o nome da pasta onde está localizado a API no 'directory'.

##Configuração Apache2

Para o funcionamento correto da API em um servidor Apache2, precisamos criar urls amigaveis e deixar o Kep cuidar do assunto.

	RewriteEngine On
	RewriteCond %{REQUEST_FILENAME} !-f
	RewriteCond %{REQUEST_FILENAME} !-d
	RewriteRule .index.php [L]

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
