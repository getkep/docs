##Authentication

Usamos uma camada de autenticação do usuário, onde o mesmo que consome os dados da API, envie o nome de usuário e uma token, onde o mesmo e comparado com a $_SESSION["token"] e no banco de dados.

##User/Email

A arquitetura que consome a API, envia o nome de usuário ou email para comparar no sistema.

##Token

A token, pode ser numeros e letras aleatorios, gerados pelo seu sistema e adicionado a uma sessão. Token gerada a cada novo login do usuário em seu sistema.

##Configuração
Para configurar o sistema de autenticação é preciso alterar o seu arquivo de configuração na pasta raiz..

    'authentication' => [
        'mysql' => [
            'activate' => true,
            'table' => 'Tabela',
            'column' => 'Coluna',
        ],
    ],    