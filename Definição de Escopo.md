Definição de escopo


* Index
   * Cadastrar empresa:
      * Cadastro de produtos.
   * Login:
      * Fornecedor;
      * Restaurante;
* Menu
   * Restaurante
      * Cadastrar usuários;
      * Cotações;
         * Pedido de cotação;
         * Avaliar cotação
            * Aprovar;
            * Recusar.        
      * Visualizar estoque;
         * Visualizar nível do estoque;
         * Baixa de estoque;
         * Entrada de produtos;


   * Fornecedor
      * Cadastrar produto;
      * Avaliar cotações;
         * Aprovar ;
         * Recusar.


* Fornecedor - Cadastrar sua empresa.
                        
* Atributos:
   * Documento;
   * Tipo do documento. - CPF ou CNPJ;
   * Nome;
   * Data de nascimento;
   * Cidade;
   * Email;
   * Senha;
   * Confirmar senha;
*  Regra de negócio:
   * Usuário criado fica inativo até aprovação do adm;
   * Usuário criado vai para aprovação;
   * Confirmação de e-mail;
   * Disparar e-mail com o resultado, aprovado ou não;
   * CNPJ ou CPF.
      * Validação de CNPJ - http://www.macoratti.net/alg_cnpj.htm;
      * Validação de CPF - https://dicasdeprogramacao.com.br/algoritmo-para-validar-cpf/;
   * Senha e confirmar senha deve ser iguais, 6 caracteres, não pode ser o mesmo nome do usuário, não pode ter espaço em branco.


* Cadastro de produtos:


* Regras de negócio:
   * Após o preenchimento do cadastro do fornecedor, chamar tela de cadastro de produtos que o mesmo pode fornecer;
   * Os campos deverão ter o formato checkbox, e cada fornecedor pode escolher um ou mais produtos;
   * Os campos de checkbox devem vir todos desmarcados;
* Atributos:
   * Item 
      * Qual item o mesmo pode oferecer;
   * Categoria 
      * Tipo do item Ex.(Item -> Arroz, Categoria-> Branco ou Integral);


Obs: Verificar junto ao restaurante popular se é interessante para eles que no ato do cadastro de produtos que um fornecedor oferece ele informe a marca de cada produto, ou se é melhor que isso seja informado apenas na cotação.




* Estoque - entrada de produtos.
                        
* Atributos:
   * Produto;
   * Quantidade;
   * Localização, qual estoque está;
   * Data de validade.
* Regra de negócio:
   * Validar produto;
   * Validar data.








* Pedido de cotação:
   * Restaurante:
      * Atributos:
      * Nível de estoque;
      * Botão verificar níveis; chama tela de verificação do estoque
         * Tabela de itens:
            * Descrição do Item;
            * Marca
            * Quantidade que contem no momento;
            * Quantidade necessária de compra;
            * Fornecedor;
            * Marcar em vermelho todos os produtos que estiverem em nível mínimo de estoque;
            * Marcar em amarelo todos os itens que estiverem em 20% acima do nível mínimo de estoque;
      * Checkbox:
         * Ao lado de cada item para marcar quais serão solicitados na cotação.
      * Botão envio de cotação:
         * Mostrar todos os itens do pedido;
         * Estabelecer a data de vencimento da cotação;
         * Confirmar pedido.
        
   * Regras de Negócio:
      * Comprador recebe aviso de nível mínimo de estoque;
      * Após confirmar cotação, será enviado um e-mail para todos os possíveis fornecedores que se cadastraram para vender tais produtos;
      * A cotação deve ter um período de aceitação, se o fornecedor não aceitar, retirar o pedido da sua visão;
   * Fornecedor:        
      * Atributos:
         * Aceitar ou rejeitar cotação;        
         * Visão do pedido;
         * Guia de cotação;
            * Preencher cotação:
               * Descrição do produto;
               * Categoria;
               * Quantidade em Kg;
               * Marca;
               * Preço;
               * Validade;
         * 













DB:
comida.catolica@gmail.com
senha: comida.catolica@2019
