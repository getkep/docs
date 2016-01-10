##Controller

Os controles são utilizados para realizar as suas funções que ira retornar algum objeto, exemplo: queremos fazer a multiplicação de um dado vindo da nossa rota "2" e multiplicar por 2, vejamos isto em um exemplo básico.

##Controller Básico

Para criarmos um controller é preciso seguir algumas regras basicas de nossa Framework, confira em [Getting started](/#/docs).

Vamos criar a nosso primeiro controller e conhecer a estrutura padrão de um Controller Kep.

	use KepPHP\Kep\controller\BaseController;
    
	class NomeDoController extends BaseController{
    
    	private $params ;
    	
     	function __construct($parameters){
         	$this->params = $parameters;
    	 }
    	
	}

##Parameters

Para podermos obter os parâmetros recebidos atraves dos metodos Post, Get, Put e Delete, utilizamos o var $params.

O retorno dos parâmetros vindo do metodo Post, Put e Delete é JSON, para utilizarmos, vejamos o exemplo:

	$this->params->number

Para o metodo Get, o Kep retorna um array, confira o exemplo:

	$this->params['number'];

##Response

Para retornarmos os valores e os resultados que fizemos dentro de nosso controller, utilizamos o método response() da nossa BaseController.

Retornamos os valores em formato JSON.

	$array = array (
    	"mensagem" => "mensagem a retornar"
	);
    
	$this->response($array);

O **Number** é o nome do parametro que espera receber e compartilhar pelo controller ou model.

##Meu primeiro controller

Veja um exemplo de nossa Route utilizando a função getMulti() de nosso controller.

	use KepPHP\Kep\controller\BaseController;
    
	class MyController extends BaseController{
    
    	private $params;
    
    	function __construct($parameters){
        	$this->params = $parameters;
    	}
    
     	public function getMulti(){
         	$Multiplication = 2 * $this->params->number;
        
         	$this->response($Multiplication);
     	}
    
	}

Para que possamos utilizar uma rota que use o nosso controller "MyController" e a função getMulti(), confira.

	Route::post('getMulti', ['uses' => 'MyController@getMulti']);

Para entender mais sobre Route, leia em [Routing](/#/docs/routing).

##Controller mais Model

Quando precisamos efetuar alguma conexão com o banco de dados, para obtermos alguns dados. No Kep, utilizamos o Model, para que possamos efetuar está conexão, para saber mais sobre o funcionamento, leia em [Model](/#/docs/model).