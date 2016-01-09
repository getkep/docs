##Query Builder

Para utilizarmos o model para conexões com o banco de dados, precisamos utilizar o Query Builder do Kep.

##Conexão

Antes de comerçamos é preciso configurar o arquivo config.php, siga o [Getting Started](/#/docs).

##Select

Para efetuarmos uma seleção em nosso banco de dados é bem simples, veja um exemplo.

	$select = DB::select( 'SELECT * FROM Users' );

Para o uso do WHERE, existe algumas regras, para adicionar um valor coresponde a coluna, precisamos adicionar em uma matriz em ordem, veja um exemplo.

	$select = DB::select( 'SELECT * FROM Users WHERE Nome = ?' , [ 'Matuzalem' ]);

Podemos percebe que utilizamos a "interrogação" na frente do "Nome =", isto significa que estamos falando para o Kep preencher o espaço de acordo a ordem que passamos na matriz.

O nossa query retorna uma array com os valores, confira.

	$select ['num_rows'];
	$select ['fetch_array'];

Para podermos guarda ou utilizar os dados do fetch_array, utilizamos o foreach, vejamos um exemplo.

	foreach($select['fetch_array'] as $fetch){
	}

##Update

Para podermos efetuar um update em nosso banco de dados, utilizamos uma pequena regra do Kep.

	$update = DB::update( 'UPDATE Users SET Nome = ?, Tag = ?' , [ 'Matuzalem' , 'PHP' ]);

Para utilizar o WHERE em nosso query, utilizamos a mesma forma acima, confira.

	$update = DB::update( 'UPDATE Users SET Nome = ?, Tag = ? WHERE Nome = ?' , [ 'Matuzalem' , 'PHP' , 'Fulano' ]);

O query builder do Kep, sempre retorna alguns dados do resultado da query em uma array, confira um exemplo.

	$update [ 'affected' ];

##Insert

Para inserirmos uma query em nosso banco de dados, utilizamos uma regra do Kep.

	$insert = DB::insert( 'INSERT INTO Users(Nome, Tag) VALUES(?, ?)' , [ 'Matuzalem' , 'PHP' ]);

O query builder do Kep, sempre retorna alguns dados do resultado da query em uma array, confira um exemplo.

	$insert [ 'affected' ];
	$insert [ 'insert_id' ];

##Delete

Para deletarmos uma coluna de nosso banco de dados, utilizamos uma regra do Kep.

	$delete = DB::delete( 'DELETE * FROM Users' );

Para deletar uma coluna especifica, utilizamos o WHERE, confira a nossa query no Kep.

	$delete = DB::delete( 'DELETE * FROM Users WHERE Nome = ?' , [ 'Matuzalem' ]);

O query builder do Kep, sempre retorna alguns dados do resultado da query em uma array, confira um exemplo.

	$delete [ 'affected' ];

##Delimitando

Para utilizar comandos no fim de uma query, como 'LIMIT' e 'ORDER BY'. No Kep, fazemos da seguinte forma.

	$select = DB::select( 'SELECT * FROM Users WHERE Nome = ?' , [ 'Matuzalem' ], 'ORDER BY id DESC LIMIT 1' );