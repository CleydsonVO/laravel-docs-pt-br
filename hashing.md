# Hashing

- [Introdu��o](#introducao)
- [Uso b�sico](#uso-basico)

<a name="introducao"></a>
## Introdu��o

O facade `Hash` do Laravel, fornece um seguro hash Bcrypt para armazenar senhas de usu�rios. Se voc� estiver usando o controller `AuthController` que est� incluso na sua aplica��o Laravel, ele ser� respons�vel por verificar as senhas Bcrypt contra as vers�es un-hashed fornecidas pelo usu�rio.

Da mesma forma, o servi�o `Registrar` que vem com o Laravel faz uma chamada apropriada da fun��o `bcrypt` para senhas armazenadas.

<a name="uso-basico"></a>
## Uso b�sico

#### Criando um Hash usando Bcrypt

	$password = Hash::make('secret');

Voc� tamb�m pode usar a fun��o helper `bcrypt`;

	$password = bcrypt('secret');

#### Verificando uma senha contra um Hash

	if (Hash::check('secret', $hashedPassword))
	{
		// As senhas conincidem...
	}

#### Verificando se precisa criar um Hash para a senha

	if (Hash::needsRehash($hashed))
	{
		$hashed = Hash::make('secret');
	}
