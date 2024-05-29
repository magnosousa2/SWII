Boa noite, pessoal!

Segue atividade para ser desenvolvida durante a aula de hoje.  

Deixei algumas dicas no final do exercício, principalmente sobre a inserção de registros na base de dados, pois foi um assunto que mal introduzimos e iríamos aprofundar na aula de hoje.  

Tentem adaptar os exercícios já praticados em sala de aula, pois são bem semelhantes. 

Não se preocupem se não conseguirem finalizar hoje, sei que é um exercício relaticamente complicado, mas não deixem de tentar. 

Façam em dupla. Caso não terminem hoje, na próxima aula estarei aí para auxiliá-los. 



EXERCÌCIO PROPOSTO:

Vamos criar uma aplicação de controle de transações financeiras de um banco.

Nossa aplicação precisará de duas tabelas:
 - Uma para controle de saldo do cliente, contendo as seguintes colunas: CPF_CLIENTE, NOME CLIENTE, SALDO_CONTA
 - Uma para controle das transações realizadas pelo cliente, contendo as seguintes colunas: COD_AUTORIZACAO, VALOR_TRANSACAO, CPF_CLIENTE, STATUS_TRANSACAO (aprovada, negada)
 
 
 Precisaremos de 5 endpoints:
 
	POST /cadastrar-cliente (para inserir o registro de um novo cliente na tabela CLIENTES)
	POST /inserir-transacao (para inserir o registro da transação aprovada ou negada na tabela TRANSACOES)
	GET /consultar-transacoes (para consultar todas as trasnações da tabela TRANSACOES)
	GET /consultar-transacoes/:CPF_CLIENTE ( Usando URL parameter para consultar as transações de um 			determinado CPF)
	GET /consultar-transacoes?CPF_CLIENTE=XXX&STATUS_TRANSACAO=XXX (Usando query strings para consultar as transações de um determinado CPF por STATUS_TRANSAÇÃO)
	
	
	Obs: Ao tentar inserir um registro de transação, deve-se validar se o valor da transação é menor que o saldo do cliente.
		Se saldo maior que valor transação, então:
			-insere registro de transação aprovada na tabela TRANSACOES. 
			-atualiza o saldo do cliente na tabela CLIENTE)
		Se saldo menor que valor transação, então:
			- insere registro de transação negada na tabela TRANSACOES.
			- Não modifica o saldo na tabela CLIENTE.
			
	

	Dica:
		Para os métodos POST, vocês precisarão recuperar as informações recebidas no corpo da requisição (req.body). Esse corpo deve ser transmitido em formado de um objeto json. Por exemplo, para o cadastro do cliente ficaria o seguinte ao enviar a requisição pelo HTTP REST CLIENT(Aquele plugin do VSCODE):
		
		{
			CPF_CLIENTE: 'xxxxxxxxx',
			NOME CLIENTE: 'Fulano de Tal',
			SALDO_CONTA: 12000		
		}


		
	Dica2:
		Siga o passo a passo:
			- Crie o banco de dados e as tabelas
			- Crie a aplicação node e instale as dependências:
				- npm install express, mysql2, nodemon
			- Baixe o plugin REST Client no VSCODE para poder fazer os testes dos endpoints
			- Lembre-se de quebrar o problema por partes e ir refatorando à medidade que for necessário, por exemplo: crie primeiro os endpoints e teste se está funcionando, depois de funcionando, implemente a lógica de tratamento dos dados no banco de dados. 
			
		    - Teremos inserts, updates e selects no banco de dados.
		
			
			
			
	
