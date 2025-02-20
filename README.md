# Sobre o AdventureWorks 2022
O AdventureWorks é um varejista de equipamentos esportivos fictícios da Microsoft. Ela representa uma empresa multinacional de médio ou grande porte 

# Objetivo do Projeto
Este projeto analisa as vendas da empresa fictícia do AdventureWorks, utilizando o SQL Server para armazenamento e modelagem dos dados e Power BI para visualização. O objetivo é identificar tendências, oportunidades de crescimento e melhorar a eficiência operacional.
<br><br>
## Consulta dos Dados no SQL
O SQL foi escolhido porque oferece mais processamento, segurança e velocidade em comparação ao Excel. Isso garante que os dados estejam sempre íntegros, impedindo alterações indevidas e evitando problemas com arquivos corrompidos ou deslocados. 
O objetivo da consulta no banco de dados no SQL é trazer uma visão geral das vendas online por região, período e categoria dos produtos.<br>
<br>
<img align="middle" width="800"  src="https://github.com/Raphaneitor/AdventureWorksPortfolio/blob/main/imagens/Query%20de%20consulta_FactInternetSales.png?raw=true">
<br>
<br>
Primeiro realizamos uma consulta simples na tabela FactInternetSales, para saber como os dados estão estruturados e quais informações podemos utilizar nas nossas futuras análises <br>
<br>
<img align="left" width="350" height="500" src="https://github.com/Raphaneitor/AdventureWorksPortfolio/blob/main/imagens/colunas_FactInternetSales.png?raw=true">
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
Continuamos a nossa análise observando as colunas da Tabela FactInternetSales, para que possamos também identificar quais outras tabelas estão vinculadas aos eventos dessa tabela fato, através das chaves estrangeiras presentes nela.<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<img align="middle" width="800"  src="https://github.com/Raphaneitor/AdventureWorksPortfolio/blob/main/imagens/Diagrama%20de%20banco_FactInternetSales.png?raw=true">
<br>
<br>
Uma boa prática também é sempre verificar se no banco que for analisado, já possui um diagrama de relacionamento entre as suas tabelas, pois a partir daí, 
já conseguimos visualizar de forma clara quais tabelas estão relacionadas com a tabela que iremos utilizar, que no caso seria a FactInternetSales.
<br><br>


## Integração SQL Server - Power BI
É eficiente tanto em praticidade, segurança e facilidade analisar o banco de dados no SQL Server, mas para visualização de dados há somente tabelas. Com o Power BI, é possível demonstrar com mais opções de gráficos interativos os dados da empresa, moldados de acordo com a preferência do usuário final. O primeiro passo é a integração do SQL Server ao Power BI.
Passo a passo:
1.	Abrir o Power BI Desktop.
2.	Clicar em "Obter Dados" no menu superior.
3.	Selecionar "SQL Server" como fonte de dados.
4.	Preencher os detalhes da conexão, como servidor e o nome do banco de dados criado.
5.	Clicar em "Conectar".
<img align="middle" width="800"  src="https://github.com/Raphaneitor/AdventureWorksPortfolio/blob/main/imagens/import%20banco%20de%20dados.png?raw=true">
Nota: caso queira utilizar o modo de conectividade de dados o de Importar, aumentará consideravelmente o tamanho do seu arquivo .pbix, pois ele irá baixar para o arquivo em questão todas as tabelas que forem selecionadas na hora da importação.
<br>
<br>
Já a opção de DirectQuery, ele fará um link direto com o banco de dados e não precisara baixar as tabelas, porem caso queira abrir esse arquivo de outro lugar, 
as tabelas não estarão disponíveis para visualização no powerBI, e sendo assim, veja qual a opção se encaixa melhor a sua situação.
<br><br>

## Relacionamento e modelagem dos dados
<img align="middle" width="800"  src="https://github.com/Raphaneitor/AdventureWorksPortfolio/blob/main/imagens/Modelo%20relacional%20de%20dados_AdventureWorks.png?raw=true">
<b> Tabelas e colunas importadas, criadas e modeladas:</b> <br><br>
<b> - 1) FactInternetSales:</b> Base para calcular métricas de desempenho, como total de vendas, ticket médio e quantidade de produtos vendidos.<br><br>
<b> ProductKey:</b> Chave estrangeira para a tabela de dimensão de produtos (DimProduct). Indica qual produto foi vendido.<br><br>
<b> OrdersDateKey:</b> Chave estrangeira para a tabela de dimensão de datas (DimCalendário). Representa a data em que a venda ocorreu.<br><br>
<b> DueDateKey:</b> Chave estrangeira para a tabela de dimensão de datas (DimCalendário). Representa a data de vencimento da entrega do produto da venda.<br><br>
<b> ShipDateKey:</b> Chave estrangeira para a tabela de dimensão de datas (DimCalendário). Representa a data em que a venda foi encaminhada.<br><br>
<b> CustomerKey:</b> Chave estrangeira para a tabela de dimensão de clientes (DimCustomer). Indica qual cliente realizou a compra.<br><br>
<b> PromotionKey: </b>Chave estrangeira para a tabela de dimensão de descontos/promoções (DimPromotion). Indica se a venda teve alguma promoção/desconto.<br><br>
<b> CurrencyKey:</b> Chave estrangeira para a tabela de dimensão de moedas (DimCurrency).Indica qual tipo de moeda foi realizada na venda.<br><br>
<b> SalesTerritoryKey:</b> Chave estrangeira para a tabela de dimensão de território (DimSalesTerritory). Indica em qual região foi realizada a compra do produto.<br><br>
<b> SalesOrderNumber:</b> Chave Primária para a tabela de FactInternetSales. Representa o ID/número da venda.<br><br>
<b> SalesOrderLineNumber:</b> Chave Primária para a tabela de FactInternetSales. Representa a linha da ordem da venda.<br><br>
<b> RevisionNumber:</b> Representa o número de revisões da ordem de pedido.<br><br>
<b> OrderQuantity: </b>Representa o número de pedidos da ordem de pedido.<br><br>
<b> UnitPrice:</b> Preço unitário do produto (quanto o cliente pagou).<br><br>
<b> ExtendedAmount:</b> Representa o montante estendido ao valor do produto.<br><br>
<b> UnitPriceDiscountPct:</b> Representa o desconto encima do preço unitário do produto (quanto o cliente pagou).<br><br>
<b> DiscountAmount:</b> Representa o desconto encima do preço amontoado da venda (quanto o cliente pagou).<br><br>
<b> TotalProductCost:</b> Representa o custo total do produto (quanto a empresa pagou por ele).<br><br>
<b> SalesAmount:</b> Valor total da venda.<br><br>
<b> TaxAmt:</b> Taxa encima do valor da venda.<br><br>
<b> Freight:</b> Valor do frete para a entrega do produto.<br><br>
<b> CarrierTrackingNumber:</b> Numero de rastreio para a entrega.<br><br>
<b> CustomerPONumber:</b> O número de ordem de compra do cliente.<br><br>
<b> OrderDate:</b> Data em que a venda ocorreu.<br><br>
<b> DueDate:</b> Data de vencimento da entrega do produto da venda.<br><br>
<b> ShipDate:</b> Data em que a venda foi encaminhada.<br><br>
<br>
<b> - 2) DimProduct: </b>Permite análises por produto individual, como identificação dos itens mais vendidos ou com maior margem de lucro.<br><br>
<b> ProductKey:</b> Chave Primária para a tabela de DimProduct. Representa o ID/número do produto.<br><br>
<b> ProductAlternateKey:</b> Outro número que serve para representar o ID/número do produto.<br><br>
<b> ProductSubcategoryKey:</b> Chave estrangeira para a tabela de subcategoria de produtos (DimProductSubcategory). Indica qual subcategoria de produto foi vendido.<br><br>
<b> WeightUnitMeasureCode:</b> Código de medida de peso da unidade do produto.<br><br>
<b> SizeUnitMeasureCode:</b> Código de medida de tamanho da unidade do produto.<br><br>
<b> EnglishProductName: </b>Nome em Inglês do produto.<br><br>
<b> SpanishProductName:</b> Nome em Espanhol do produto.<br><br>
<b> FrenchProductName: </b>Nome em Francês do produto.<br><br>
<b> StandardCost: </b>Custo inicial do produto.<br><br>
<b> FinishedGoodsFlag:</b> Numero que representa a ordem de demanda dos produtos.<br><br>
<b> Color:</b> Cor do Produto.<br><br>
<b> SafetyStockLevel: </b>Numero de produtos extra no estoque para possíveis altas demandas.<br><br>
<b> ReorderPoint:</b> Número do ponto de reabastecimento.<br><br>
<b> ListPrice:</b> Preço listado do produto.<br><br>
<b> Size:</b> Tamanho do produto.<br><br>
<b> SizeRange:</b> Faixa de tamanho do Produto.<br><br>
<b> Weight: </b>Peso do produto.<br><br>
<b> DaysToManufacture: </b>Dias para a produção/reabastecimento do produto.<br><br>
<b> ProductLine:</b> Linha do Produto<br><br>
<b> DealerPrice:</b> Preço do revendedor.<br><br>
<b> Class: </b>Classe do produto.<br><br>
<b> Style:</b> Estilo do produto.<br><br>
<b> ModelName: </b>Nome do modelo do produto.<br><br>
<b> LargePhoto:</b> Tamanho e foto do produto.<br><br>
<b> EnglishDescription:</b> Descrição em Inglês do produto.<br><br>
<b> FrenchDescription:</b> Descrição em Francês do produto.<br><br>
<b> ChineseDescription: </b>Descrição em Chines do produto.<br><br>
<b> ArabicDescription:</b> Descrição em Árabe do produto.<br><br>
<b> HebrewDescription: </b>Descrição em Hebreu do produto.<br><br>
<b> ThaiDescription:</b> Descrição em Tailandês do produto.<br><br>
<b> GermanDescription:</b> Descrição em Alemão do produto.<br><br>
<b> JapaneseDescription:</b> Descrição em Japonês do produto.<br><br>
<b> TurkishDescription:</b> Descrição em Turco do produto.<br><br>
<b> StartDate:</b> Data de começo da disponibilidade do produto em estoque para venda.<br><br>
<b> EndDate:</b> Data do fim da disponibilidade do produto em estoque para venda.<br><br>
<b> Status:</b> Informa se o produto está em estoque ou não.<br><br>
<br>
<b> - 3) DimProductSubCategory:</b> Adiciona um nível intermediário de categorização entre o produto e a categoria principal, permitindo análises mais refinadas.<br><br>
<b> ProductSubcategoryKey:</b> Chave primária da tabela, usada para identificar cada subcategoria de produto de forma única. Também funciona como chave estrangeira na tabela (DimProduct).<br><br>
<b> ProductCategoryKey:</b> Chave estrangeira que referência a tabela DimProductCategory, indicando a qual categoria a subcategoria pertence.<br><br>
<b> ProductSubcategoryAlternateKey:</b> Outro número que serve para representar o ID/número da subcategoria do produto.<br><br>
<b> EnglishProductSubcategoryName:</b> Informa o nome da subcategoria do produto em Inglês.<br><br>
<b> SpanishProductSubcategoryName:</b> Informa o nome da subcategoria do produto em Espanhol.<br><br>
<b> FrenchProductSubcategoryName:</b> Informa o nome da subcategoria do produto em Francês.<br><br>
<br>
<b> - 4) DimProductCategory:</b> Permite agrupar os produtos em categorias amplas para análises estratégicas.<br><br>
<b> ProductCategoryKey:</b> Chave primária da tabela, usada para identificar cada categoria de produto de forma única. Também é referenciada na tabela DimProductSubCategory.<br><br>
<b> ProductCategoryAlternateKey:</b> Outro número que serve para representar o ID/número da categoria do produto.<br><br>
<b> EnglishProductCategoryName:</b> Informa o nome da categoria do produto em Inglês.<br><br>
<b> SpanishProductCategoryName:</b> Informa o nome da categoria do produto em Espanhol.<br><br>
<b> FrenchProductCategoryName:</b> Informa o nome da categoria do produto em Francês.<br><br>
<br>
<b> - 5) DimPromotion:</b> Permite agrupar quais produtos possuem algum tipo de promoção/desconto.<br><br>
<b> PromotionKey:</b> Chave primária da tabela, usada para identificar cada tipo de promoção de forma única. Também é referenciada na tabela FactInternetSales.<br><br>
<b> PromotionAlternateKey:</b> Outro número que serve para representar o ID/número do tipo de promoção do produto.<br><br>
<b> EnglishPromotionName:</b> Nome da promoção do produto em Inglês.<br><br>
<b> SpanishPromotionName:</b> Nome da promoção do produto em Espanhol.<br><br>
<b> FrenchPromotionName:</b> Nome da promoção do produto em Francês.<br><br>
<b> DiscountPct:</b> Preço do desconto da promoção<br><br>
<b> EnglishPromotionType:</b> Nome do tipo de promoção do produto em Inglês.<br><br>
<b> SpanishPromotionType:</b> Nome do tipo de promoção do produto em Espanhol.<br><br>
<b> FrenchPromotionType:</b> Nome do tipo de promoção do produto em Francês.<br><br>
<b> EnglishPromotionCategory:</b> Nome da categoria da promoção em Inglês.<br><br>
<b> SpanishPromotionCategory:</b> Nome da categoria da promoção em Espanhol.<br><br>
<b> FrenchPromotionCategory:</b> Nome da categoria da promoção em Francês.<br><br>
<b> StartDate:</b> Data de início da promoção.<br><br>
<b> EndDate:</b> Data de fim da promoção.<br><br>
<b> MinQty:</b> Quantidade mínima para o produto entrar na promoção na hora da venda.<br><br>
<b> MaxQty:</b> Quantidade máxima para o produto entrar na promoção na hora da venda.<br><br>
<br>
<b> - 6) DimCurrency:</b> Agrupa quais tipos de moeda podem ser utilizadas nas vendas.<br><br>
<b> CurrencyKey:</b> Chave primária da tabela, usada para identificar qual tipo de moeda de forma única. Também é referenciada na tabela FactInternetSales.<br><br>
<b> CurrencyAlternateKey:</b> Outro número que serve para representar o ID/número do tipo de moeda.<br><br>
<b> CurrencyName:</b> Nome/Sigla da Moeda utilizada na hora da venda.<br><br>
<br>
<b> - 7) DimCustomer:</b> Permite agrupar as informações de todos os clientes das vendas.<br><br>
<b> CustomerKey:</b> Chave primária da tabela, usada para identificar o cliente de forma única. Também é referenciada na tabela FactInternetSales.<br><br>
<b> GeographyKey:</b> Chave estrangeira para a tabela de dimensão de região (DimGeography). Indica de qual região o cliente realizou a compra.<br><br>
<b> CustomerAlternateKey:</b> Outro número que serve para representar o ID/número do cliente.<br><br>
<b> Title: </b>Informa um possível título para o cliente.<br><br>
<b> FirstName:</b> Informa o primeiro nome do cliente.<br><br>
<b> MiddleName: </b>Informa o nome do meio do cliente.<br><br>
<b> LastName:</b> Informa o ultimo nome do cliente.<br><br>
<b> NameStyle:</b> Informa um possível estilo para o nome do cliente.<br><br>
<b> BirthDate:</b> informa a data de nascimento do cliente.<br><br>
<b> MaritalStatus:</b> Informa o estado civil do cliente.<br><br>
<b> Suffix:</b> Informa um possível sufixo no nome do cliente.<br><br>
<b> Gender:</b> Informa o gênero do cliente.<br><br>
<b> EmailAddress: </b>informa o e-mail do cliente.<br><br>
<b> YearlyIncome:</b> informa o quanto o cliente ganha em um ano.<br><br>
<b> TotalChildren: </b>informa o número total de filhos do cliente.<br><br>
<b> NumberChildrenAtHome:</b> Informa o número de filhos/crianças que o cliente possui em casa.<br><br>
<b> EnglishEducation:</b> Informa o nível de educação do Cliente em Inglês.<br><br>
<b> SpanishEducation:</b> Informa o nível de educação do Cliente em Espanhol.<br><br>
<b> FrenchEducation:</b> Informa o nível de educação do Cliente em Francês.<br><br>
<b> EnglishOccupation:</b> Informa o tipo de ocupação do Cliente em Inglês.<br><br>
<b> SpanishOccupation:</b> Informa o tipo de ocupação do Cliente em Espanhol.<br><br>
<b> FrenchOccupation:</b> Informa o tipo de ocupação do Cliente em Francês.<br><br>
<b> HouseOwnerFlag:</b> Número que serve para identificar se o cliente é o proprietário da residência em que vive.<br><br>
<b> NumberCarsOwned:</b> numero de carros que o cliente possui.<br><br>
<b> AddressLine1: </b>endereço informado pelo cliente.<br><br>
<b> AddressLine2: </b>possível segundo endereço informado pelo cliente.<br><br>
<b> Phone: </b>numero de telefone do cliente.<br><br>
<b> DateFirstPurchase: </b>Data da primeira compra do cliente.<br><br>
<b> CommuteDistance:</b> Distancia de deslocamento do cliente.<br><br>
<br>
<b> - 8) DimGeography: </b>Crucial para entender padrões de consumo por área.<br><br>
<b> GeographyKey: </b>Chave primária da tabela, usada para identificar cada localização de forma única. Também é referenciada por outras tabelas, como DimCustomer, para associar os clientes a uma localização específica.<br><br>
<b> SalesTerritoryKey: </b>Chave estrangeira para a tabela de dimensão de Território de vendas (DimSalesTerritory). Indica de qual região o cliente realizou a compra.<br><br>
<b> City:</b> Informa a Cidade<br><br>
<b> StateProvinceCode: </b>Informa o código/sigla da Província/Estado<br><br>
<b> StateProvinceName:</b> Informa o nome da Provincia/Estado<br><br>
<b> CountryRegionCode:</b> Informa o código/sigla da região.<br><br>
<b> EnglishCountryRegionName: </b>Informa o nome do país/região em Inglês.<br><br>
<b> SpanishCountryRegionName: </b>Informa o nome do país/região em Espanhol.<br><br>
<b> FrenchCountryRegionName:</b> Informa o nome do país/região em Francês.<br><br>
<b> PostalCode: </b>Informa o código postal<br><br>
<b> IpAddressLocator:</b> Informa o endereço de IP da localização.<br><br>
<br>
<b> - 9) DimSalesTerritory: </b>Tabela que serve para categorizar/sumarizar de quais regiões estão sendo realizadas as compras.<br><br>
<b> SalesTerritoryKey:</b> Chave primária da tabela, usada para identificar cada região de forma única. Também é referenciada por outras tabelas, como DimGeography, para associar os clientes a uma localização específica.<br><br>
<b> SalesTerritoryAlternateKey:</b> Outro número que serve para representar o ID/número da região.<br><br>
<b> SalesTerritoryRegion:</b> Informa o nome da região da venda.<br><br>
<b> SalesTerritoryCountry:</b> Informa o nome do país da venda.<br><br>
<b> SalesTerritoryGroup:</b> Informa o nome do grupo/continente da venda.<br><br>
<b> SalesTerritoryImage:</b> Mostra a imagem da região.<br><br>
<br>
<b> - 10) DimCalendário:</b> Fundamental para análises temporais, como tendências de vendas ou sazonalidade.<br><br>
<b> Ano:</b> Representa o ano da data (exemplo: 2024).<br><br>
<b> Trimestre:</b> Número do trimestre do ano (1 para janeiro a março, 2 para abril a junho, etc.)<br><br>
<b> Quarter: </b>Geralmente uma versão em inglês do trimestre, usada para análises internacionais.<br><br>
<b> Date:</b> Representação completa da data no formato YYYY-MM-DD (exemplo: 2024-02-12).<br><br>
<b> Dia: </b>Número do dia do mês (exemplo: 12 para 12 de fevereiro).<br><br>
<b> Dia da Semana:</b> Número do dia na semana (1 para domingo, 2 para segunda-feira, etc.).<br><br>
<b> Nome do dia:</b> Nome do dia da semana (exemplo: "Segunda-feira").<br><br>
<b> Mês:</b> Número do mês dentro do ano (1 para janeiro, 2 para fevereiro, etc.).<br><br>
<b> Mês abrev:</b> Nome do mês abreviado (exemplo: "Jan", "Fev", "Mar").<br><br>
<b> Nome do Mês:</b> Nome completo do mês (exemplo: "Janeiro", "Fevereiro").<br><br>
<b> Semana do Ano: </b>Número da semana dentro do ano (1 para a primeira semana de janeiro, 2 para a segunda, etc.).<br><br>
<b> Semana do Mês:</b>  Número da semana dentro do mês (1 para a primeira semana do mês, 2 para a segunda, etc.).<br><br>
<b> YearMonth:</b> Representação do ano e do mês no formato YYYYMM (exemplo: 202402 para fevereiro de 2024).<br><br>
<b> YearMonth desc:</b> Representação do ano e do mês no formato YYYYMM (exemplo: 202402 para fevereiro de 2024) em ordem decrescente.<br><br>
<br>

## Medidas

Seguindo com a nossa análise, agora criaremos uma nova tabela para organizar nossas medidas, indo em modelagem e depois em nova tabela. 
Vamos criar as medidas DAX para calcular o total de vendas, custos, margem de lucro, quantidade de vendas e vendas acumuladas no ano.<br>

<img align="middle" width="500"  src="https://github.com/Raphaneitor/AdventureWorksPortfolio/blob/main/imagens/Medidas/Sales%20Amount.png?raw=true">

<b> - Sales Amount:</b> Ajuda a identificar o desempenho das vendas em diferentes períodos, regiões ou categorias.<br>

<img align="middle" width="500"  src="https://github.com/Raphaneitor/AdventureWorksPortfolio/blob/main/imagens/Medidas/Sales%20Amount%20LY.png?raw=true">

<b> - Sales Amount LY (vendas do ano anterior):</b> Ajuda a identificar a magnitude das vendas em diferentes períodos, regiões ou categorias.<br>

<img align="middle" width="500"  src="https://github.com/Raphaneitor/AdventureWorksPortfolio/blob/main/imagens/Medidas/Sales%20Amount%20LY%20Delta.png?raw=true">

<b> - Sales Amount LY Delta (diferença de vendas):</b> Mostra o ganho ou perda de vendas em números.<br>

<img align="middle" width="500"  src="https://github.com/Raphaneitor/AdventureWorksPortfolio/blob/main/imagens/Medidas/Sales%20Amount%20LY%20Delta%20%25.png?raw=true">

<b> - Sales Amount LY Delta %: </b>Oferece uma perspectiva proporcional para entender a taxa de crescimento ou retração.<br>

<img align="middle" width="500"  src="https://github.com/Raphaneitor/AdventureWorksPortfolio/blob/main/imagens/Medidas/Sales%20Delta%20%25%20txt.png?raw=true">

<b> - Sales Delta % txt: </b>medida com formatação pré-estabelecida para mostrar em forma de texto a % da diferença de valores de venda entre um período com o outro.<br>

<img align="middle" width="500"  src="https://github.com/Raphaneitor/AdventureWorksPortfolio/blob/main/imagens/Medidas/Cost.png?raw=true">

<b> - Cost: </b>Permite monitorar o impacto das despesas operacionais nas finanças da empresa.<br>

<img align="middle" width="500"  src="https://github.com/Raphaneitor/AdventureWorksPortfolio/blob/main/imagens/Medidas/Cost%20%25.png?raw=true">

<b> - Cost %: </b>Mostra a taxa de crescimento ou redução dos custos.<br>

<img align="middle" width="500"  src="https://github.com/Raphaneitor/AdventureWorksPortfolio/blob/main/imagens/Medidas/Cost%20LY.png?raw=true">

<b> - Cost LY (custo do ano anterior):</b> Permite identificar tendências de aumento ou redução de custos ao longo do tempo.<br>

<img align="middle" width="500"  src="https://github.com/Raphaneitor/AdventureWorksPortfolio/blob/main/imagens/Medidas/Cost%20LY%20Delta.png?raw=true">

<b> - Cost LY Delta: </b>Ajuda a identificar áreas específicas onde os custos cresceram ou foram otimizados.<br>

<img align="middle" width="500"  src="https://github.com/Raphaneitor/AdventureWorksPortfolio/blob/main/imagens/Medidas/Cost%20LY%20Delta%20%25.png?raw=true">

<b> - Cost LY Delta %: </b>Mostra a taxa de crescimento ou redução dos custos, proporcionalmente ao ano anterior.<br>

<img align="middle" width="500"  src="https://github.com/Raphaneitor/AdventureWorksPortfolio/blob/main/imagens/Medidas/Cost%20delta%20%25%20txt.png?raw=true">

<b> - Sales Delta % txt: </b>medida com formatação pré-estabelecida para mostrar em forma de texto a % da diferença de valores de custo entre um período com o outro.<br>

<img align="middle" width="500"  src="https://github.com/Raphaneitor/AdventureWorksPortfolio/blob/main/imagens/Medidas/Gross%20Margin.png?raw=true">

<b> - Gross Margin: </b>Ajuda a identificar o valor de lucro gerado pela empresa em um período.<br>

<img align="middle" width="500"  src="https://github.com/Raphaneitor/AdventureWorksPortfolio/blob/main/imagens/Medidas/Gross%20Margin%20%25.png?raw=true">

<b> - Gross Margin %: </b>Mostra a taxa de crescimento ou redução na margem de lucro da empresa.<br>

<img align="middle" width="500"  src="https://github.com/Raphaneitor/AdventureWorksPortfolio/blob/main/imagens/Medidas/Gross%20Margin%20LY.png?raw=true">

<b> - Gross Margin LY:</b> Permite comparar a lucratividade atual com o desempenho histórico.<br>

<img align="middle" width="500"  src="https://github.com/Raphaneitor/AdventureWorksPortfolio/blob/main/imagens/Medidas/Gross%20Margin%20LY%20Delta%20.png?raw=true">

<b> - Gross Margin LY Delta: </b>Ajuda a identificar áreas específicas (regiões, produtos, categorias) onde a lucratividade foi impactada positivamente ou negativamente.<br>

<img align="middle" width="500"  src="https://github.com/Raphaneitor/AdventureWorksPortfolio/blob/main/imagens/Medidas/Gross%20Margin%20LY%20Delta%20%25.png?raw=true">

<b> - Gross Margin LY Delta %:</b> Ajuda a avaliar a eficácia das estratégias de controle de custos e aumento de vendas.<br>

<img align="middle" width="500"  src="https://github.com/Raphaneitor/AdventureWorksPortfolio/blob/main/imagens/Medidas/Gross%20Margin%20Delta%20%25%20txt.png?raw=true">

<b> - Gross Margin Delta % txt:</b> medida com formatação pré-estabelecida para mostrar em forma de texto a % da diferença de valores de margem bruta entre um período com o outro.<br>

<img align="middle" width="500"  src="https://github.com/Raphaneitor/AdventureWorksPortfolio/blob/main/imagens/Medidas/Sales%20Quantity.png?raw=true">

<b> - Sales Quantity:</b> Crucial para entender o volume de vendas e acompanhar o desempenho geral da empresa.<br>

<img align="middle" width="500"  src="https://github.com/Raphaneitor/AdventureWorksPortfolio/blob/main/imagens/Medidas/Sales%20Quantity%20LY%20.png?raw=true">

<b> - Sales Quantity LY (quantidade de vendas do ano passado):</b> Fundamental para avaliar o crescimento ou declínio nas quantidades de vendas.<br>  

<img align="middle" width="500"  src="https://github.com/Raphaneitor/AdventureWorksPortfolio/blob/main/imagens/Medidas/Sales%20Quantity%20LY%20Delta.png?raw=true">

<b> - Sales Quantity LY Delta:</b> Ajuda a identificar o impacto das mudanças no volume de vendas, revelando se as vendas estão aumentando ou diminuindo.<br>

<img align="middle" width="500"  src="https://github.com/Raphaneitor/AdventureWorksPortfolio/blob/main/imagens/Medidas/Sales%20Quantity%20LY%20Delta%20%25.png?raw=true">

<b> - Sales Quantity LY Delta %: </b>Ela é fundamental para apresentar o impacto das flutuações nas quantidades de vendas de maneira compreensível.<br>

<img align="middle" width="500"  src="https://github.com/Raphaneitor/AdventureWorksPortfolio/blob/main/imagens/Medidas/Sales%20Quantity%20Delta%20%25%20txt.png?raw=true">

<b> - Sales Quantity Delta % txt:</b> medida com formatação pré-estabelecida para mostrar em forma de texto a % da diferença de valores de quantidade de vendas entre um período com o outro.<br>

<img align="middle" width="500"  src="https://github.com/Raphaneitor/AdventureWorksPortfolio/blob/main/imagens/Medidas/Discount.png?raw=true">

<b> - Discount:</b> Ajuda a identificar os valores de desconto nas vendas pela empresa em um período.<br>

<img align="middle" width="500"  src="https://github.com/Raphaneitor/AdventureWorksPortfolio/blob/main/imagens/Medidas/Sales%20Last%20Date.png?raw=true">

<b> - Sales Last Date:</b> medida utilizada para mostrar a data da ultima venda de um determinado período.<br>

<img align="middle" width="500"  src="https://github.com/Raphaneitor/AdventureWorksPortfolio/blob/main/imagens/Medidas/Sales%20Year%20to%20Date.png?raw=true">

<b> - Sales Year to Date:</b> Importante para acompanhar o desempenho de vendas em tempo real ao longo do ano, ajudando a analisar se a empresa está cumprindo suas metas de vendas anuais.<br>

<img align="middle" width="500"  src="https://github.com/Raphaneitor/AdventureWorksPortfolio/blob/main/imagens/Medidas/Sales%20Year%20to%20Date%20Last%20Year.png?raw=true">

<b> - Sales Year to Date Last Year:</b> Essencial para medir o desempenho de vendas em relação ao ano anterior e observar tendências de crescimento ou declínio.<br>


<br><br>

## Principais métricas do dashboard e Conclusão do projeto
<img align="middle" width="800"  src="https://github.com/Raphaneitor/AdventureWorksPortfolio/blob/main/imagens/AdventureWorks_neon_Dashboard_Overview.png?raw=true">
<img align="middle" width="800"  src="https://github.com/Raphaneitor/AdventureWorksPortfolio/blob/main/imagens/AdventureWorks_neon_Dashboard_Detail.png?raw=true">
<b> - Card de quantidade de vendas:</b> Mostra o volume total de unidades vendidas, útil para avaliar a demanda.<br><br>
<b> - Card de vendas:</b> Destaca o total de vendas, fornecendo um indicador rápido do desempenho geral.<br><br>
<b> - Card de custos:</b> Ajuda a monitorar os gastos, essencial para avaliar a eficiência operacional.<br><br>
<b> - Card de Margem de lucro:</b> Demonstra a rentabilidade da empresa, combinando vendas e custos.<br><br>
<b> - Tipo de Produto:</b> Mostra quais os principais tipos de produtos vendem na Empresa. No caso do Adventure Works, na maior parte do tempo,
mais de 96% das vendas são de bicicletas, fazendo que ela tenha total dependência sobre esse tipo de produto. Como sugestão, seria melhor criar mais descontos 
na parte de acessórios e roupas por exemplo, para tentar diversificar os lucros com um maior número de vendas.<br><br>
<b> - Vendas por país:</b> Identifica os mercados mais rentáveis e permite análises geográficas estratégicas. Os EUA, juntamente da Australia,
lideram as vendas por uma boa margem em relação aos outros países. Com isso, sugerimos campanhas específicas para o mercado Americano e Australiano,
como promoções sazonais nos períodos de férias/feriados ou de eventos relacionados ao ciclismo da região.<br><br>
<b> - Vendas por Subcategoria de produtos:</b> Revela quais produtos ou categorias têm maior impacto nas vendas, apoiando decisões de portfólio. 
TOP 3 produtos mais vendidos representam mais de 95% das vendas totais. Isso mostra que o AdventureWorks, por mais que tenha
tem um portfólio diversificado, tem grande dependência de poucos produtos, o que aumenta riscos financeiros<br><br>
<b> - Venda por mês:</b> Permite identificar sazonalidades, tendências mensais e períodos de pico ou queda. Detectamos uma queda sazonal no início do ano e sugerimos promoções estratégicas, como “Volta às Aulas”, para minimizar o impacto.<br><br>
<b> - Vendas acumuladas:</b> Compara o desempenho do ano atual com o anterior, ajudando a monitorar o progresso e planejar ações corretivas. <br><br>
<b> - Filtros dinâmicos:</b> Permitem personalizar as visualizações, tornando os dados relevantes para diferentes usuários e contextos.<br><br>
<b> - Tooltips (detalhamento):</b> Oferecem informações adicionais ao passar o cursor, enriquecendo as análises sem poluir o layout.<br><br>
<b> - Drill-through (tabela de detalhe das vendas):</b> Oferecem informações detalhadas ao selecionar qualquer medida com o botão direito e selecionar o Drill-through para o dashboard de vendas online detalhes, deixando as analises muito mais profundas.<br><br>

<br><br>
## Conclusão
Este projeto demonstra como a análise de dados pode transformar informações brutas em decisões estratégicas. Com insights claros sobre tendências de vendas, 
sazonalidade e lucratividade, as empresas podem ajustar suas estratégias para maximizar o crescimento e a eficiência operacional.

## Ferramentas e linguagens utilizadas
<div style="display: inline_block">
    <img align="center" alt="SQL" height="40" width="40" src="https://github.com/Raphaneitor/Portfolio/blob/main/linguagens/sql.png?raw=true">
    <img align="center" alt="Power BI" height="40" width="40" src="https://github.com/Raphaneitor/Portfolio/blob/main/linguagens/power%20bi.png?raw=true">
</div>
