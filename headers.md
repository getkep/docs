##Headers

Para podermos melhorar a segurança de nossas APIs, utilizamos as Headers ao nosso favor. O Kep tem pequenas configurações da Header, não deixe de contribuir para podermos melhorar.

##Access control allow origin

Com isso, podemos definir qual domínio ou ip pode acessar a nossa API ou liberar com uso do "*".
    
    use GetKep\Kep\headers\header;

	header::allowOrigin( "http://getkep.com" );
    
	Route::post("allUsers", ['uses' => ['MyController@allUsers']);

##Access control allow headers

Podemos adicionar mais informações a nossa header.
	
	use GetKep\Kep\headers\header;
    
	header::contentType("Content-Type, Access-Control-Allow-Headers, Authorization, X-Requested-With");

##Content type

Podemos definir os dados que a API pode receber. Confira em ação.

	use GetKep\Kep\headers\header;
    
	header::contentType("application/x-www-form-urlencoded, multipart/form-data, text/plain");