##Seeds

Os seeds são utilizados para adicionar complementos ou snippets em sua aplicação, podendo está utilizando a nossa função em todos os nossos controllers, deixando as nossas funções reutilizáveis e saudáveis.

##Configuração

Para adicionar os nossos seeds em nossa aplicação, bastamos acessar a nossa página Seeds e criar o arquivo com o nome do nosso seed, siga as regras em nosso [Getting Started](/#/docs).

##Seed básica

O nome da classe de nossa seed, tem que ser iguais ao nome do arquivo sem a extensão '.php'.

vejamos o exemplo de nossa primeira seed. Seeds.php

	class Seeds{
    
    	// Functions
    
	}

##Seed no controller

Para podermos utilizar a nossa seed em nosso controller, precisamos fazer o load, confira como se faz no Kep.

	use KepPHP\Kep\controller\BaseController;
    
	class NomeDoController extends BaseController{
    
     	private $seed ;
    
     	function __construct(){
         	$this->seed = $this->seeds('seeds');
     	}
    
	}