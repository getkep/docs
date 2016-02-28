##Model

Para a criação de Models é preciso seguir algumas regras de nossa Framework, leia mais em [Getting started](/#/docs)

##O que são?

O Model é utilizado em junção com o [Controller](/#/docs/controller), é capaz de efetuar conexões com o banco de dados.

##Model Básica

Vamos criar um model básica para servir o controller, iremos conhecer a estrutura do model do Kep.

	use KepPHP\Kep\database\DB;
	use KepPHP\Kep\model\BaseModel;

	class mymodel extends BaseModel{

    	// Functions

	}

##Dependência do controller

Para poder utilizar o model e a suas funções é preciso utilizar a depedencia do controller, vejamos como poderemos chamar o nosso model no controller.

	use KepPHP\Kep\controller\BaseController;

	class MyController extends BaseController{

    	private $load ;

    	function __construct(){
        	$this->load = $this ->model('mymodel');
    	}

	}

Para organizamos melhor os nossos models em pastas, como o exemplo abaixo.

	api/
		 ├─ v1/
		 │    ├─ controllers/
		 │    ├─ models/
		 │    ├─── auth/
		 │    └─ seeds/
		 └─ vendor/

Podemos chamar a nossa model da seguinte forma.

	$this->load = $this ->model('mymodel', 'auth');
