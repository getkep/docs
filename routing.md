##Routing

A criação de rotas é o ponto inicial para poder distribuir a sua API para ser consumida.

PS: Para começar é preciso que tenha lido o [Getting Started](/#/docs).

##Routing Básico

Para criarmos a nossa routing, utilizamos o arquivo index.php de acordo às [regras](/#/docs) da framework.

	require_once ( "../vendor/autoload.php" );
    
	use KepPHP\Kep\route\Route;
    
	/* Criando route com dependência do Controller */
	Route::post( "allUsers" , [ 'uses' => [ 'MyController@allUsers' ]);
    
	/* Criando route sem dependência do Controller */
	Route::post( "Endpoint" , function (){
    	// Tarefas para retorna
	});

##Post

O sistema de rotas para obter os dados enviado via Post é bem facil no Kep Framework, vejamos um exemplo deixando a dependencia para o controller.

	Route::post( "Endpoint" , [ "uses" => "NomeDoController@FunctionAExecutar" ]);

Criando uma rota sem dependencia do controller também é facil.

	Route::post( "Endpoint" , function (){
     	// Tarefas para retorna
	});

##Get

Podemos obter dados vindo do metodo GET, veja como é facil.

	Route::get( "user/:id" , [ "uses" => "NomeDoController@FunctionAExecutar" ]);

Para obter o valor da Get dentro do controller eu poderia obter desta maneira.

	$this ->params[ 'id' ];

O valor id é coresponde ao declarado no route.

Para podermos utilizar o parametro recebido atraves da get sem a dependencia do controller.

	Route::get( "salvar/:id" , function ( $parameters ){
     	echo $parameters [ 'id' ] ;
	});

O Kep ele retorna uma matriz com os paramêtros contidos na variavel $parameters para metodos Get.

##Put

Metodo put, normalmente utilizado para API de atualização de dados, confira o modo de uso com a dependencia do controller.

	Route::put( "save" , [ "uses" => "NomeDoController@FunctionAExecutar" ]);

Para efetuar uma ação rapida sem a dependencia do controller.

	Route::put( "save" , function (){
     	// Tarefas para retorna
	});

##Delete

Podemos enviar dados pelo metodo HTTP delete para a API, sendo facil o modo de deletar informações do banco de dados.

	Route::delete( "user/delete" , [ "uses" => "NomeDoController@FunctionAExecutar" ]);

Sem a dependencia do controller.

	Route::delete( "user/delete" , function (){
     	// Tarefas para retorna
	});

##Grupos de Route

Com o grupo de routes, podemos determinar uri fixas para o inicio de chamadas às API, assim podemos construir diferentes versões de nossa aplicação no mesmo arquivo.

	Route::group( 'api/v1' , function (){
     	// Rotas
	});
    
	Route::group( 'api/v2' , function (){
     	// Rotas
	});

##Response

Retornando valores é magico é facil, utilizamos o uso de uma array para guarda os dados que queremos retorna em nossa API e utilizamos o método "response" que retorna em JSON.

Observação: usado sem a dependencia do controller e com a dependencia no controller.

	$array = array (
     	"mensagem" => "mensagem a retornar"
	);
    
	$this ->response( $array );