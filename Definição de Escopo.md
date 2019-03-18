
    **Definição de escopo**



*   **Index**
    *   Cadastrar fornecedor:
        *   Cadastro de produtos.
    *   Login:
        *   Usuário;
        *   Senha.

Obs: O próprio usuário e senha definirá o papel de cada usuário.



*   **Menu**
    *   **Restaurante;**
        *   Cadastrar usuários;
        *   Cotações;
            *   Pedido de cotação;
            *   Avaliar cotação;
                *   Aprovar;
                *   Recusar.	
        *   Estoque;
            *   Visualizar nível do estoque;
            *   Baixa de estoque;
            *   Entrada de produtos;
            *   Últimas movimentações.
    *   **Fornecedor;**
        *   Cadastrar produto;
        *   Avaliar cotações;
            *   Aprovar ;
            *   Recusar.
        *   Visualização do pedido;
        *   Envio de cotação.
            *   **Desktop KPI**
                *   Restaurante
                    *   Número de cotações pendentes de avaliação.
        *   Nível de estoque;
        *   Validade de produtos(Produtos vencendo);	
        *   Aprovação de fornecedores em espera;
*   **Cadastro de Fornecedor.**

**			**



*   Atributos:
    *   Documento;
        *   Tipo do documento. - CPF ou CNPJ;
    *   Nome;
    *   Cidade;
    *   Estado;
    *   Município;
    *   CEP;
    *   Email;
    *   Senha;
    *   Confirmar senha;
    *   Qualidade;
    *   Custo;
        *   Alto;
        *   Médio;
        *   Baixo.
    *   Prazo de entrega;
*    Regra de negócio:
    *   Usuário criado vai para aprovação;
    *   Caso não ocorrer a aprovação do fornecedor, não terá nenhum bloqueio para o mesmo;
    *   Ao ter seu cadastro avaliado o fornecedor recebe um e-mail de comunicado Aprovado/reprovado;
    *   Após a avaliação do fornecedor e seu status estiver negado, bloquear seu acesso;
    *   Confirmação de e-mail;
    *   CNPJ ou CPF.
        *   Validação de CNPJ - [http://www.macoratti.net/alg_cnpj.htm](http://www.macoratti.net/alg_cnpj.htm);
        *   Validação de CPF - [https://dicasdeprogramacao.com.br/algoritmo-para-validar-cpf/](https://dicasdeprogramacao.com.br/algoritmo-para-validar-cpf/);
    *   Senha e confirmar senha deve ser iguais, 6 caracteres, não pode ser o mesmo nome do usuário, não pode ter espaço em branco.
*   **Cadastro de produtos:**
*   Regras de negócio:
    *   Após o preenchimento do cadastro do fornecedor, chamar tela de cadastro de produtos que o mesmo pode fornecer;
    *   Os campos deverão ter o formato checkbox, e cada fornecedor pode escolher um ou mais produtos;
    *   Os campos de checkbox devem vir todos desmarcados;
*   Atributos:
    *   Item 
        *   Qual item o mesmo pode oferecer;
    *   Categoria 
        *   Tipo do item Ex.(Item -> Arroz, Categoria-> Branco ou Integral);

Obs: Verificar junto ao restaurante popular se é interessante para eles que no ato do cadastro de produtos que um fornecedor oferece ele informe a marca de cada produto, ou se é melhor que isso seja informado apenas na cotação.



*   **Entrada de produtos.**
    *   Estoque
        *   Entrada de produto
            *   Conferência;
                *   Atributos:
                    *   Produto;
                    *   Quantidade;
                    *   Armazém;
                    *   Data de validade;
                    *   Categoria;
                    *   Marca/Fabricante.
                *   Regras de negócio:
                    *   Na tela de conferência. é apresentado todos os pedidos pendentes de entrega, ao selecionar um pedido é aberto todos os itens que o compõe.
                    *   Cada item é apresentado com um ícone checkbox para confirmação do recebimento e entrada no estoque, eles vem todos marcados por default, e caso o pedido não esteja completo não possibilita a entrada do pedido referido no estoque.
                    *   O campo quantidade deve ser descrito em gramas;
                    *   O armazém vem com uma sugestão do sistema, vinculado ao armazém de solicitação do pedido de compra;
                    *   A data de validade é requisito obrigatório de preenchimento;
                    *   Categoria, vem preenchida com uma sugestão do sistema, vinculada ao pedido de compra emitido;
                    *   Marca/Fabricante, vem com uma sugestão do sistema, que esteja vinculada ao pedido de compra.

**			**



*   **Pedido de cotação:**
    *   **Restaurante:**
        *   Pedido de Cotação:
            *   Recebe aviso de item com baixo nível de estoque
            *   Atributos:
                *   Verificar níveis de estoque;
                    *   Tabela de itens:
                        *   Descrição do Item;
                        *   Marca/Fabricante;
                        *   Fornecedor;
                        *   Quantidade que contem no momento;
                        *   Quantidade necessária de compra;
                        *   Marcar em vermelho todos os produtos que estiverem em nível mínimo de estoque;
                        *   Marcar em amarelo todos os itens que estiverem em 20% acima do nível mínimo de estoque;
                    *   Checkbox:
                        *   Ao lado de cada item para marcar quais serão solicitados na cotação.
                    *   Envio de Cotação:
                        *   Mostrar todos os itens do pedido;
                        *   Estabelecer a data de vencimento da cotação;
                        *   Confirmar pedido.
            *   Regras de Negócio:
                *   Comprador recebe aviso de nível mínimo de estoque;
                *   Após confirmar cotação, será enviado um e-mail para todos os possíveis fornecedores que se cadastraram para vender tais produtos;
                *   A cotação deve ter um período de aceitação, estabelecido pelo comprador, no ato da liberação da cotação, se o fornecedor não aceitar, retirar o pedido da sua visão, sempre que chegar nessa situação, encaminhar e-mail para o comprador;
                *   Só receberá o e-mail de pedido de cotação os fornecedores que oferecem todos os produtos contidos na cotação;
    *   **Fornecedor:**
        *   Visualizar cotação;
            *   Aceitar ou rejeitar cotação:
                *   Rejeitado, fim.
                *   Aceito, preencher guia de cotação;
                    *   Atributos:
                        *   Descrição do produto;
                        *   Categoria;
                        *   Marca/Fabricante;
                        *   Quantidade em Kg;
                        *   data de validade;
                        *   Preço;
                        *   Prazo de entrega.
                    *   Regras de Negócio:
                        *   Todos os campos na guia de cotação são obrigatórios;
                        *   Caso ultrapasse o tempo proposto pelo comprados de duração da cotação, ela sai da visão do fornecedor;
                        *   Após aprovação de uma cotação pelo comprador, o sistema envia o e-mail de aviso para o fornecedor, o mesmo pode aceitar ou rejeitar novamente;
                        *   Caso aceite, é gerado pedido de compra;
                        *   Caso rejeite é enviado para o próximo fornecedor com melhor preço ou a escolha do comprador e assim por diante;
*   **Baixa de estoque:**
    *   Recebe guia de requisição de retirada de produto;
        *   Atributos:
            *   Descrição;
            *   Marca/Fabricante;
            *   Quantidade disponível;
            *   Data de validade;
        *   Regras de negócio:
            *   O estoquista faz a busca por um produto Ex.(Arroz)

                o sistema traz a sugestão todos os produtos que tem no referido armazém;

            *   Os produtos são ordenados por prazo de validade, do que está mais próximo do vencimento para o que está mais distante;
            *   Ao escolher um determinado item, abre uma tela apenas para informar a quantidade que será retirada em kg;
            *   Após confirmação de baixa é atualizado a quantidade contida em estoque;
            *   Para devoluções o estoquista deve acessar, Últimas movimentações;
*   **Visualizar nível do estoque:**
    *   Escolher o Armazém de verificação:
        *   Atributos:
            *   Descrição;
            *   Categoria;
            *   Marca/Fabricante;
            *   Quantidade Atual;
            *   Quantidade mínima necessária;
            *   Data de validade;
            *   Fornecedor;
        *   Regras de negócio:
            *   Quando um item estiver 20% acima do nível mínimo de estoque, toda a linha deve estar na cor amarela;
            *   Quando o item estiver no nível mínimo ou abaixo do mesmo, toda a linha deve estar em vermelho;
            *   Os demais itens com a cor preta;
            *   Ordenação do item que estiver com maior defasagem para o menor.
*   **Últimas movimentações:**
    *   Atributos:
        *   Identificador do tipo de movimentação;
        *   Data da movimentação;
        *   Hora da movimentação;
        *   Usuário que realizou;
        *   Mais detalhes.
            *   Descrição;
            *   Categoria;
            *   Marca/Fabricante;
            *   Quantidade movimentada;
            *   Data de validade;
            *   Fornecedor;
    *   Regras de Negócio:
        *   O identificador é a descrição da movimentação. Ex. (Entrada no estoque, Baixa de estoque);
        *   Ao clicar em mais detalhes é apresentado os detalhes dessas movimentações;
        *   Caso haja devolução de produtos, na tela de mais detalhes, será possível editar essa movimentação;
        *   Caso seja editado, a movimentação será gerada uma nova movimentação em nome do usuário, com a descrição, devolução de item em estoque.

Obs: Verificar se na edição da movimentação podemos restringir essa edição a quantidade de item movimentada apenas para devoluções de produtos.

	

