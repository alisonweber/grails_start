# Projeto Grails START - Gestão de Vendas 
![GitHub repo size](https://img.shields.io/github/repo-size/iuricode/README-template?style=for-the-badge)

## Sobre o projeto

Este é um projeto piloto mantido pela <a href="https://crawsistemas.com">Craw Sistemas</a> para estimular a iniciação e aprendizagem do Framework GRAILS(<a href="https://grails.org/">https://grails.org/</a>). Este projeto está descrito e documentado utilizando os padrões projetos aplicados nos produtos da empresa. As ferramentas e versões utilizadas serão:
* Grails 3.3.11
* Banco de dados Postgres 9.4

> **Se deseja trabalhar conosco, mostre seu diferencial estudando e implementando este projeto**. Estamos a disposição para ajudar no que precisar!

<!--### Porque GRAILS?
Ainda esta na dúvida porque iniciar este estudo no framework Grails, vai aí alguns motivos: -->

### 💻 Pré-requisitos
Antes de começar, verifique se você atendeu aos seguintes requisitos:
* Disposição e vontade em adquirir novos conhecimentos.
* Conhecimentos básicos em Teoria de Orientação a Objetos.
* Conhecimentos básicos em Banco de dados.
* Tem uma máquina com `<Windows / Linux / Mac>`. O framework é multiplataforma e pode ser instalado em qualquer sistema operacional que rode a plataforma `Java`.
* JDK 1.8 instalado. Download para `Windows` disponível na pasta `requisitos`.

## Configuração Java

No `Windows` acesse as configurações de variáveis de ambiente do sistema e realize as alterações abaixo ou utilize os seguintes comandos para `Linux`:

- Criar variável de ambiente chamada JAVA_HOME:
```
export JAVA_HOME=<PATH DA INSTALAÇÃO JDK 1.8>
```

- Adicionar JAVA_HOME ao path do dispositivo:
```
export PATH="$PATH:$JAVA_HOME/bin
```

## Instalando o Grails

Download do framework:
```
https://objects.githubusercontent.com/github-production-release-asset-2e65be/512295/8a84e000-ef8a-11e9-8a56-9e869421dbd8?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAIWNJYAX4CSVEH53A%2F20211126%2Fus-east-1%2Fs3%2Faws4_request&X-Amz-Date=20211126T130926Z&X-Amz-Expires=300&X-Amz-Signature=e16ac77985e8843cef602f3809d70705df81b09319a03df9642db4959413e7a7&X-Amz-SignedHeaders=host&actor_id=34774584&key_id=0&repo_id=512295&response-content-disposition=attachment%3B%20filename%3Dgrails-3.3.11.zip&response-content-type=application%2Foctet-stream
```
* Extraia o conteúdo do download realizado e defina uma nova variável de ambiente chamada GRAILS_HOME para o local onde você extraiu o `zip`.
  - Em sistemas Linux, isso normalmente é feito da seguinte maneira: 
  ```
  export GRAILS_HOME=<PATH DA DESCOMPACTAÇÃO GRAILS>
  ```
  - No Windows, basta definir uma variável de ambiente em `My Computer/Advanced/Environment Variables`

* Em seguida, adicione a pasta `bin` à sua variável `PATH`:
  - Em sistemas Linux, isso pode ser feito adicionando 
  ```
  export PATH="$PATH:$GRAILS_HOME/bin'
  ```
  - No Windows, isso é feito modificando a variável de ambiente `PATH`

Com estas etapas realizadas o framework já esta instalado e pronto para uso :clap:. Para testar seu funcionamento, execute o comando `grails -version` em seu terminal e a resposta esperada deverá ser:
```
Grails version: 3.3.11
```
Para mais informações acesse a documentação oficial <a href="http://docs.grails.org/3.3.11/guide/single.html#gettingStarted">clicando aqui</a>.

# Definições do projeto
Criar um sistema WEB para gestão de Vendas, utilizando o framework Grails e salvando os registros em um banco de dados Postgres. 

Nos próximos itens serão apresentados alguns diagramas para ajudar no entendimento do projeto. Os diagramas foram desenvolvidos utilizando a ferraments <a herf="https://staruml.io/">StartUML</a>. Uma <a href="https://github.com/alisonweber/grails_start/blob/01959c20fd48eb34e522ff3eab7e3b9c5b477a0f/ModeloStarUML.mdj">cópia do modelo</a> esta presente neste projeto.

### Use Case Diagram
O diagrama abaixo apresenta o usuário do sistema (também conhecidos como ator) e as interações dele com o sistema. Nele poderá ver os cenários que devem ser desenvolvidos e o escopo geral do sistema.

![image](https://user-images.githubusercontent.com/34774584/143625127-33866ed8-0179-4ad7-98c8-9e572c1ac3f1.png)

### Class Diagram
O diagrama abaixo ilustra os modelos de dados para o sistema a ser desenvolvido, apresentando uma visão geral dos esquemas e necessidades da aplicação.

![image](https://user-images.githubusercontent.com/34774584/143627093-eef14618-4a28-4278-ac60-55fd07f299ce.png)

### Regras para os Modelos
	Usuário
	- nome: obrigatório, tamanho máximo de 255
	- usuario: obrigatório, tamanho máximo de 50 //Atributo utilizado para realizar o login no sitema
	- senha: obrigatório, tamanho máximo de 50, deve possuir letras e números

	Produto
	- nome: obrigatório, tamanho máximo de 255
	- valorPadrao: facultativo //Atributo utilizado para carregar o valor padrão do produto durante a digitação de uma Venda
	
	Cliente
	- nome: obrigatório, tamanho máximo de 255
	- cpfCnpj: obrigatório, validar se preenchimento é de tamanho 11 ou 14 digitos compostos apenas de números;
	- email: facultivo, validar se é e-mail valido;
	
	Venda
	- cliente: obrigatório
	- valorTotal: obrigatório, maior que 0.00 //somatório de todos os itens da venda
	- itensVenda: obrigatóroo, deve possuir ao menos 1 item
	
	VendaItem
	- produto: obrigatório
	- valorUnitario: obrigatório //carregar automaticamente ao selecionar um produto cadastrado do atributo valorPadrao
	- quantidade: obrigatório, maior que 0.00
	- desconto: facultativo
	- valorTotalItem: obrigatóroo, maior que 0.00 // valorTotalItem = (valorUnitario * quantidade) - desconto
	
## Criando o projeto

[FAZER] Explicar como criar um projeto.

### Primeiro CRUD

[FAZER] Explicar a criação do primeiro domínio.

### CRUD de Exemplo

[FAZER] Explicar o que foi feito.

## Para nos enviar seu código, você pode:

- Fazer um fork desse repositório, e nos mandar uma pull-request.
- Dar acesso ao seu repositório privado no Gitlab para o usuário <definir>.
	
### Avaliação
	
- Iremos verificar o código do projeto e como foi solucionado. Não hesite em nos surpreender positivamente.
- Gostariamos de uma explicação da solução e do aprendizado que teve. Poderá ser oral ou em arquivo de texto separado em Markdown/Plain Text.
