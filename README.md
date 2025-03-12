# desafio_dio2

1. Modelagem Lógica do Banco de Dados para E-commerce:

    Entidades e Atributos:
        Cliente:
            ID_Cliente (PK)
            Nome
            Endereço
            Cliente PF:
                ID_Cliente (FK)
                CPF
                RG
                Data_Nascimento
            Cliente PJ:
                ID_Cliente (FK)
                CNPJ
                Inscrição_Estadual
                Nome_Fantasia
        Produto:
            ID_Produto (PK)
            Nome
            Descrição
            Preço
        Pedido:
            ID_Pedido (PK)
            ID_Cliente (FK)
            Data_Pedido
            Status
        Produto_Pedido:
            ID_Produto (FK)
            ID_Pedido (FK)
            Quantidade
        Fornecedor:
            ID_Fornecedor (PK)
            Razão_Social
            CNPJ
            Contato
        Produto_Fornecedor:
            ID_Produto (FK)
            ID_Fornecedor (FK)
            Quantidade
        Estoque:
            ID_Estoque (PK)
            ID_Produto (FK)
            Quantidade
            Localização
        Pagamento:
            ID_Pagamento (PK)
            ID_Cliente (FK)
            Tipo_Pagamento
            Detalhes_Pagamento
        Entrega:
            ID_Entrega (PK)
            ID_Pedido (FK)
            Status_Entrega
            Código_Rastreio

    Relacionamentos:
        Cliente (1) - (*) Pedido
        Cliente (1) - (*) Pagamento
        Produto (*) - (*) Pedido (Produto_Pedido - Tabela Assossiativa)
        Fornecedor (*) - (*) Produto (Produto_Fornecedor - Tabela Assossiativa)
        Produto (1) - (1) Estoque
        Pedido (1) - (1) Entrega

    Chaves Primárias e Estrangeiras:
        Defina as chaves primárias (PK) e estrangeiras (FK) conforme indicado acima.
        Garanta que as chaves estrangeiras referenciem corretamente as chaves primárias das tabelas relacionadas.

    Constraints:
        Utilize constraints para garantir a integridade dos dados (NOT NULL, UNIQUE, CHECK, etc.).
        Cliente PJ e PF, utilizar o "check" para que apenas um dos dois seja utilizado.

    Modelo EER:
        Atente-se aos relacionamentos de especialização (Cliente PF e PJ) e relacionamentos muitos-para-muitos (Produto_Pedido, Produto_Fornecedor).

2. Script SQL de Criação do Esquema:

    Utilize a linguagem SQL (DDL) para criar as tabelas, definindo os tipos de dados, chaves primárias, chaves estrangeiras e constraints.
    Organize o script de forma clara e legível.

3. Persistência de Dados para Testes:

    Insira dados de teste nas tabelas para simular um cenário real de e-commerce.
    Varie os dados para testar diferentes cenários e consultas.

4. Queries SQL Complexas:

    Recuperações Simples (SELECT):
        Exibir todos os produtos com seus respectivos preços.
        Listar todos os clientes cadastrados.
    Filtros (WHERE):
        Selecionar pedidos realizados por um cliente específico.
        Encontrar produtos com preço acima de um determinado valor.
    Atributos Derivados:
        Calcular o valor total de cada pedido (quantidade * preço).
        Exibir o nome completo do cliente, juntando nome e sobrenome, caso exista essa informação.
    Ordenação (ORDER BY):
        Listar produtos em ordem crescente de preço.
        Exibir pedidos em ordem decrescente de data.
    Filtros em Grupos (HAVING):
        Encontrar clientes que realizaram mais de X pedidos.
        Mostrar fornecedores que fornecem mais de "x" produtos.
    Junções (JOIN):
        Exibir o nome do cliente, o número do pedido e a lista de produtos comprados.
        Listar fornecedores e os produtos que eles fornecem.
