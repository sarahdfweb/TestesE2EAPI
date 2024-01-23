# Protocolos de API 🚧 Em construção ....
> REST 
Representational State Transfere é uma API de serviços da web; A arquitetura REST é simples e fornece acesso aos recursos para que o cliente REST acesse e reenderizeos recursos no lado do cliente. No estilo REST, URI ou IDsglobais ajudam a identificar cada recurso; Está arquitetura usa várias representações de recursos para representar seu tipo, como XML, JSON, Texto, Imagens e assim por diante.
 
> Restfull

Uma API que segue todos os princípios de arquitetura é chamada de RESTful. 
Stateless - A API REST é statelesspor natureza, onde o servidor não precisa saber em qual estado o cliente está e vice-versa 
Interface uniforme - um cliente e um servidor devem se comunicar um com o outro via HTTP (protocolo de transferência de hipertexto) usando URIs(identificadores de recursos exclusivos), CRUD (criar, ler, atualizar, excluir) e convenções JSON (JavaScriptObjectNotation). 
> Cliente-servidor - o cliente e o servidor devem ser independentes um do outro. As alterações feitas no servidor não devem afetar o cliente e vice-versa. 
> Cache - o cliente deve armazenar em cache as respostas, pois isso melhora a experiência do usuário, tornando-as mais rápidas e eficientes. 
Em camadas - a API deve oferecer suporte a uma arquitetura em camadas.
HTTP Status Code
Cada resposta que a aplicação REST retorna, é enviado um código definindo o status da requisição:


# HTTP Status Code

<details>
  <summary><b>Exemplos de 2xx: Sucesso</b></summary>
  
  > A requisição foi recebida com sucesso, entendida e aceita. 
  
  > - **200 OK** – Resposta padrão de sucesso 
  > - **201 Created** – Indica que um recurso foi criado 
  > - **202 Accepted** – Indica que a requisição foi aceita 
  > - **204 No Content** – Indica que a requisição foi processada com sucesso, mas que não há conteúdo para retornar
</details>

<details>
   <summary><b>Exemplos de 4xx: Erro do cliente </b></summary> 
  
   > Ação que ocorre um erro do cliente/servidor.
  
   > - **400 BadRequest** – A requisição com problemas (Ex: mudanças de contrato)
 
  > - **401 Unauthorized** – Cliente não autenticado ou sem autorização

  > - **403 Forbidden** –  Cliente autenticado, mas sem permissão
 
  > - **404 Notfound** –  Recurso não localizado

</details>

<details>
    <summary><b> Exemplos de 5xx: Erro do servidor </b></summary> 
  
> Ação que ocorre um erro do servidor 
> - **500 InternalServer Error** –  Um erro ocorreu durante o processamento da requisição (erro no processamento) 
> - **503 Service Unavailable** –  Serviço indisponível (por manutenção ou sobrecarga)

</details>


# Métodos HTTP 
> O protocolo HTTP (Hypertext TransferProtocol) define um conjunto de métodos de requisição responsáveis por indicar a ação a ser executada para um dado recurso; 
> Também são chamados de Verbos HTTP.  Os principais são GET, POST, PUT, DELETE; Outros métodos HEAD, CONNECT, OPTIONS, TRACE, PATCH.

<details>
   <summary><b> Método GET </b></summary> 
Enviada pelo cliente para solicitar dados de um recurso no servidor.🚧...
 
Ao fazer uma requisição GET, você está solicitando informações do servidor e esperando que ele retorne os dados correspondentes.
Por exemplo.: Se você acessar a página de tênis e selecionar as opções de tamanho e cor, o site faz automaticamente uma requisição GET para a API para obter aquela opção de tênis.
 
 ![image](https://github.com/sarahdfweb/TestesE2EAPI/assets/87348787/8e6fbc76-404c-44b0-81d1-3321f845d27b)
 ## Exemplo no postman 
 ![image](https://github.com/sarahdfweb/TestesE2EAPI/assets/87348787/9b581c58-28ef-4fb4-b98f-7caad987f3a4)
  
</details>


<details>
   <summary><b> Método POST </b></summary> 
O método POST é frequentemente utilizado para criar novos recursos no servidor, criar usuários, enviar dados de formulários da web, criar postagens em redes sociais, adicionar itens ao carrinho de compras, entre outros.
Ele é uma maneira de enviar dados para o servidor para que ele possa processar e armazenar essas informações.
 
![image](https://github.com/sarahdfweb/TestesE2EAPI/assets/87348787/56a4ab8e-caa5-4516-870c-72680471815e)

![image](https://github.com/sarahdfweb/TestesE2EAPI/assets/87348787/c5727632-b36c-4dcb-84ad-011ab40bdc17)


  
</details>

<details>
   <summary><b> Método PUT </b></summary> 
O método PUT é usado em requisições HTTP para atualizar ou criar um recurso no servidor. Quando você envia uma solicitação PUT, você fornece os dados do recurso completo ou parcial que deseja atualizar. Se o recurso especificado não existe, o servidor pode criar um novo recurso com o conteúdo fornecido.
</details> 

<details>
  <summary><b> Método DELETE</b></summary> 
remove um recurso específico.
</details> 

<details>
  <summary><b>Interfaces </b></summary> 
Dividir seu sistema em muitos serviços pequenos, geralmente significa que esses serviços precisam se comunicar uns com os outros; 
Eles se comunicam através de certas interfaces de diferentes aplicativos, formas e tecnologias. 
## Os mais comuns são:
  
 REST e JSON via HTTPS RPC usando algo como gRPC Comunicações via SOAP/XML 
## Contratos

Como pode ser enviado informações para diferentes Consumers, há a necessidade de especificar claramente a interface entre esses serviços (o chamado contrato) afim de evitar problemas de integração. 
## Documentação

https://documenter.postman.com/view/631643/JsLs/?version=latest#3190c896-4216-a0a3-aa38-a041d0c2eb72

</details>

<details>
  <summary><b>O que testar?</b></summary>

1. **Status:** O código de resposta está adequado (2xx, 3xx, 4xx e 5xx);
2. **Performance:** A resposta retornou dentro do tempo adequado;
3. **Syntaxe:** O tipo de conteúdo retornado está adequado (Content-Type) / o servidor aceita requisições no formato adequado;
4. **Tratamento de erro:** O servidor rejeita requisições no formato inadequado / excluir campos obrigatórios deve resultar em erro / requisições com tipos de dados inadequados deve resultar em erro;
5. **Detecção de erros:** Testes negativos para identificar exceções;
6. **Schema:** O conteúdo da resposta está de acordo com a estrutura ou formato esperado (contrato);
7. **Funcional:** O servidor retorna o valor previsto de acordo com a requisição / a requisição insere, atualiza ou exclui um recurso esperado;
8. **Segurança:** Injeções de SQL não impactam na integridade dos dados.
</details>

<details>
   <summary><b>JSON (JavaScriptObjectNotation-Notação de Objetos JavaScript)</b></summary>
é uma formatação leve de troca de dados.
É um formato leve de troca de dados. Fácil de ler e escrever, e também é fácil para máquinas interpretarem e gerarem. JSON é comumente utilizado para a comunicação entre um servidor e um cliente web, como uma forma de estruturar dados.
Vantagens: Leitura mais simples Analisador(parsing) mais fácil JSON suporta objetos Performance na execução e transporte de dados Arquivo com tamanho reduzido.
  
## Objeto

Um objeto é um conjunto desordenado de pares nome/valor. Um objeto começa com {chave de abertura e termina com chave de fechamento }. Cada nome é seguido por: dois pontos e os pares nome/valor são seguidos por, vírgula.

 ![image](https://github.com/sarahdfweb/TestesE2EAPI/assets/87348787/4c52276a-565f-4f1d-99f2-dbfc9532320b)

## Array

Uma array é uma coleção de valores ordenados. O array começa com [ colchete de abertura e termina com colchete ] de fechamento. Os valores são separados por ,vírgula.

 ![image](https://github.com/sarahdfweb/TestesE2EAPI/assets/87348787/4728bc7a-8886-4d62-b838-85ae12fdd190)

## Valor

Um valor pode ser uma: 
cadeia de caracteres (string) um número true ou false null objeto array

![image](https://github.com/sarahdfweb/TestesE2EAPI/assets/87348787/1d1535bf-5b83-49a9-aef9-b90f1dc96ffa)


 
## Postman
O Postman é uma ferramenta que proporciona criar, compartilhar, testar e documentar APIs. Permite aos usuários criarem e salvar solicitações HTTP e HTTPs simples e complexas, bem como ler suas respostas. https://www.postman.com/downloads/
 
## ServeRest
Pré-requisito: Node JS 
Inserir o seguinte comando no console: npx serverest
Para acessar basta abrir seu navegador com a seguinte url: http://localhost:3000/ ou http://127.0.0.1:3000/ Obs.: Enquanto estiver usando, deixe o console aberto. Caso tenha problema com a instalação, use o endereço de produção: https://serverest.dev/ , mas corre o risco de alguém mexer nos seus dados, pois é um ambiente compartilhado.
</details>

# Realizando testes de API no postman de e2e (Ponta a ponta)	
## Etapas para o Teste
Funcionalidade: Usuários
* Cadastrar usuários (Método POST)
* Listar usuários cadastrados (GET)
* Buscar usuário pelo ID (GET)
* Excluir usuário (PUT)
  




<!--
Funcionalidade: Produtos 
•	Cadastrar um usuário como admin (POST)
•	Listar produtos (GET)
•	Cadastrar 2 produtos (POST)
•	Editar um dos produtos (PUT)
•	Deletar um dos produtos (DELETE)
> Utilizarei a API ServeRest Que simula uma loja virtual

1 Criar servidor local para não ficar no site para não correr o risco de alteração por outro usuário. No terminal digite (npx serverest)
2 Criar uma nova collection usei o nome Teste ServeRest
3 Criar uma Request (Requisição)
4 Adicionei o nome da request de criar usuário
5 Utilizei o método POST
6 Colei o exemplo do site e mudei os parâmetros e cliquei em send
7 Exibindo o usuário criado com o método GET
8 Fazendo login método POST
9 Criando Validação de Produtos : 
9.1 Passei a url : http://localhost:3000/produtos cliquei em send para que ele listasse os produtos cadastrados. Foi listado 2 produtos 
9.2 Validando o produto da lista usando snippets (Response body: Contains String e Status code; Code is 200)
10 Cadastrando produto 
Obs.: Necessário primeiro realizar o login, por isso precisar autorizar o login passando o token 
11 Editar um produto com método PUT
Obs.: precisa do tooken do login
 
Autorizando o token
 

Mensagem de sucesso 



Produto alterado 
 
Deletando um produto cadastrado com método DELETE
Obs.: Precisa autorizar o token do login
 
 

Token 
 
 
  
Relatório 
1 Exporta o documento 
 
2  Faça a instalação do Newman no terminal com o comando
  

3 entra na pasta que salvou o arquivo, depois digite o comando 
 
4 Também pode ser rodando em html 
 
 
Será criada uma pasta Newman com o arquivo html 
 
 -->
