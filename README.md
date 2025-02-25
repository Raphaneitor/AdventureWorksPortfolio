# Analise de desempenho de vendas Online - Adventure Works – (Projeto Power BI + SQL)

##  🔷Contexto do Projeto
Esse projeto tem como intuito analisar os dados da empresa fictícia Adventure Works, uma varejista de equipamentos esportivos fictícios da Microsoft. Considerando que ela seja uma empresa de médio-grande porte, iremos utilizar o SQL server para realizar a consulta e importação dos dados, enquanto utilizamos o Power BI para a modelagem e visualização dos mesmos. 

O Objetivo é que a partir dessa análise, possamos encontrar tendências, para assim gerar insights e alavancar o crescimento da empresa, através da otimização operacional, por exemplo.
<br><br>
## 🔷Primeiros passos:
Como todos os dados da empresa estão armazenados em um banco do SQL, iremos utilizar a ferramenta do SQL server para fazer a consulta desses dados e assim verificar o que podemos importar para a nossa ferramenta de visualização, que no caso será o Power BI. O que estamos buscando nesse início, seria encontrar os dados que trazem informações sobre as vendas online realizadas pela empresa, muito provavelmente armazenadas em uma tabela Fato, pois esses tipos de dados são classificados como eventos.<br>
<br>
<img align="middle" width="800"  src="https://github.com/Raphaneitor/AdventureWorksPortfolio/blob/main/imagens/Query%20de%20consulta_FactInternetSales.png?raw=true">
<br>
<br>
A tabela em questão seria a FactInternetSales, e através de uma consulta simples com um SELECT, podemos identificar quais são os tipos de dados encontrados em cada uma de suas colunas e através disso realizar os levantamentos necessários para encontrar quais são as outras tabelas vinculadas a essa tabela fato, conhecidas também como tabelas dimensões, pois trazem as características referentes aos eventos registrados nas tabelas fato. <br>
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
Através de uma analise mais superficial pelos nomes/tipos de colunas da tabela FactInternetSales, encontramos tanto o nome quanto o tipo das chaves primárias e estrangeiras presentes nela, e através delas, possamos identificar quais outras tabelas estão vinculadas a nossa tabela fato escolhida para a análise.<br>
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


## 🔷Próximos passos:
Através das nossas consultas realizadas no SQL, conseguimos identificar quais tabelas iremos utilizar para realizar a modelagem e visualização dos dados. O Power BI foi escolhido pois além de ele ser uma ótima ferramenta de geração de gráficos interativos e bem disseminada no mercado, ela já possui funcionalidades para extrair a base de dados diretamente do banco SQL.<br><br>
<img align="middle" width="800"  src="https://github.com/Raphaneitor/AdventureWorksPortfolio/blob/main/imagens/import%20banco%20de%20dados.png?raw=true"><br><br>
📜<b>Nota:</b> caso queira utilizar o modo de conectividade de dados o de Importar, aumentará consideravelmente o tamanho do seu arquivo .pbix, pois ele irá baixar para o arquivo em questão todas as tabelas que forem selecionadas na hora da importação.
<br>
<br>
Já a opção de DirectQuery, ele fará um link direto com o banco de dados e não precisara baixar as tabelas, porem caso queira abrir esse arquivo de outro lugar, 
as tabelas não estarão disponíveis para visualização no powerBI, e sendo assim, veja qual a opção se encaixa melhor a sua situação.
<br><br>
<img align="middle" width="800"  src="https://github.com/Raphaneitor/AdventureWorksPortfolio/blob/main/imagens/Import%20de%20dados%20Adventure%20Works%20part%202.png?raw=true"><br><br>
Assim que apertamos em conectar, em seguida irá aparecer essa janela para selecionarmos quais tabelas pretendemos extrair do banco informado, aparecendo do lado direito, uma pré-visualização dos dados da tabela selecionada.

Após selecionar todas as tabelas necessárias para a nossa analise, só precisamos clicar em “Carregar” que dai todas as tabelas serão importadas para o Power BI, e a partir disso, podemos começar a realizar as nossas modelagens.<br><br>
<img align="middle" width="800"  src="https://github.com/Raphaneitor/AdventureWorksPortfolio/blob/main/imagens/power%20query%20adventure%20works.png?raw=true"><br><br>
Após as importações das tabelas na base de dados, realizamos a alteração/formatação de tipo de dados das suas colunas pelo Power query, para garantir a integridade dos dados para as nossas analises/modelagens. Exemplo: todos os tipos de dados classificados como chaves ou ID de alguma informação, colocamos o formato do dado para texto, pois não serão feitas operações matemáticas com eles, apenas efeito de comparação com a informação em algum outro lugar.
<br><br>

## 🔷Relacionamento das tabelas/modelo de dados
<img align="middle" width="800"  src="https://github.com/Raphaneitor/AdventureWorksPortfolio/blob/main/imagens/Modelo%20relacional%20de%20dados_AdventureWorks.png?raw=true"><br><br>
Após realizamos a importação e tratamento dos dados no power query, quando vamos na aba de “exibição de modelo” no relatório do Power BI, veremos esse tipo de relacionamento entre as tabelas, mostrando de forma prioritária a tabela Fato com os seus diversos relacionamentos entre as suas tabelas dimensões.<br><br>
<b> Tabelas e colunas importadas, criadas e modeladas:</b> <br><br>
🔸<b>FactInternetSales:</b> Tabela base para se criar principais análises do projeto, sejam elas: quantidade e valor das vendas, custo sobre os produtos/vendas etc.<br><br>
<img align="middle" width="600"  src="https://github.com/Raphaneitor/AdventureWorksPortfolio/blob/main/imagens/Tabelas/FactInternetSales.png?raw=true"><br><br>
🔸<b>DimProduct: </b>Tabela que traz as características dos produtos utilizados nas vendas ou que estão cadastrados na base de dados da loja.<br><br>
<img align="middle" width="600"  src="https://github.com/Raphaneitor/AdventureWorksPortfolio/blob/main/imagens/Tabelas/DimProduct.png?raw=true"><br><br>
🔸<b>DimProductSubCategory:</b> Tabela que traz um nível a mais nas características dos produtos, tipificando a sua subcategoria.<br><br>
<img align="middle" width="600"  src="https://github.com/Raphaneitor/AdventureWorksPortfolio/blob/main/imagens/Tabelas/DimProductSubcategory.png?raw=true"><br><br>
🔸<b>DimProductCategory:</b> Tabela que traz um nível a mais nas características dos produtos, tipificando a sua categoria.<br><br>
<img align="middle" width="600"  src="https://github.com/Raphaneitor/AdventureWorksPortfolio/blob/main/imagens/Tabelas/DimProductCategory.png?raw=true"><br><br>
🔸<b>DimPromotion:</b> Tabela que traz informações sobre quais os tipos de promoções/descontos estão cadastrados para os produtos ou vendas em um determinado período.<br><br>
<img align="middle" width="600"  src="https://github.com/Raphaneitor/AdventureWorksPortfolio/blob/main/imagens/Tabelas/DimPromotion.png?raw=true"><br><br>
🔸<b>DimCurrency:</b> Tabela que traz informações sobre os tipos de moedas utilizadas nas vendas.<br><br>
<img align="middle" width="600"  src="https://github.com/Raphaneitor/AdventureWorksPortfolio/blob/main/imagens/Tabelas/DimCurrency.png?raw=true"><br><br>
🔸<b>DimCustomer:</b> Tabela que traz as informações sobre todos os clientes das vendas.<br><br>
<img align="middle" width="600"  src="https://github.com/Raphaneitor/AdventureWorksPortfolio/blob/main/imagens/Tabelas/DimCustomer.png?raw=true"><br><br>
🔸<b>DimGeography: </b>Tabela que traz informações em quais regiões foram realizadas as vendas.<br><br>
<img align="middle" width="600"  src="https://github.com/Raphaneitor/AdventureWorksPortfolio/blob/main/imagens/Tabelas/DimGeography.png?raw=true"><br><br>
🔸<b>DimSalesTerritory: </b>Tabela que serve para adicionar um nível a mais na informação de quais regiões foram realizadas as vendas.<br><br>
<img align="middle" width="600"  src="https://github.com/Raphaneitor/AdventureWorksPortfolio/blob/main/imagens/Tabelas/DimSalesTerritory.png?raw=true"><br><br>
🔸<b>DimCalendário:</b> Tabela criada para realizar as analises temporais das vendas.<br><br>
<img align="middle" width="600"  src="https://github.com/Raphaneitor/AdventureWorksPortfolio/blob/main/imagens/Tabelas/DimCalend%C3%A1rio.png?raw=true"><br><br>
Após realizamos um entendimento completo sobre as tabelas e suas informações, podemos começar a criar nossas analises por meio da linguagem DAX do Power BI, criando medidas que serão utilizadas para trazer as informações nos nossos aspectos visuais da ferramenta (cards, gráficos, filtros etc.)

Criaremos uma tabela para armazenas essas medidas, de forma a organiza-las e utilizaremos as mesmas para verificar os principais fatores para a nossa análise:<br><br>
🔹Quantidade de vendas<br><br>
🔹Total das vendas<br><br>
🔹Total de custos<br><br>
🔹Margem bruta dos lucros<br><br>
Aqui estará documentado cada uma das medidas que iremos utilizar para as nossas análises:

<img align="middle" width="500"  src="https://github.com/Raphaneitor/AdventureWorksPortfolio/blob/main/imagens/Medidas/Sales%20Amount.png?raw=true">

🔸<b>Sales Amount:</b> Serve para identificar o total das vendas.<br>

<img align="middle" width="500"  src="https://github.com/Raphaneitor/AdventureWorksPortfolio/blob/main/imagens/Medidas/Sales%20Amount%20LY.png?raw=true">

🔸<b>Sales Amount LY (vendas do ano anterior):</b> Ajuda a identificar o total das vendas com o mesmo período do ano anterior.<br>

<img align="middle" width="500"  src="https://github.com/Raphaneitor/AdventureWorksPortfolio/blob/main/imagens/Medidas/Sales%20Amount%20LY%20Delta.png?raw=true">

🔸<b>Sales Amount LY Delta (diferença de vendas):</b> Mostra em valores a diferença de vendas de um ano para o outro.<br>

<img align="middle" width="500"  src="https://github.com/Raphaneitor/AdventureWorksPortfolio/blob/main/imagens/Medidas/Sales%20Amount%20LY%20Delta%20%25.png?raw=true">

🔸<b>Sales Amount LY Delta %: </b>Mostra em forma de porcentagem a diferença de valores de venda de um ano para o outro.<br>

<img align="middle" width="500"  src="https://github.com/Raphaneitor/AdventureWorksPortfolio/blob/main/imagens/Medidas/Sales%20Delta%20%25%20txt.png?raw=true">

🔸<b>Sales Delta % txt: </b>medida com formatação pré-estabelecida para mostrar em forma de texto a % da diferença de valores de venda entre um período com o outro.<br>

<img align="middle" width="500"  src="https://github.com/Raphaneitor/AdventureWorksPortfolio/blob/main/imagens/Medidas/Cost.png?raw=true">

🔸<b>Cost: </b>Serve para mostrar o total de custo da empresa em relação as vendas.<br>

<img align="middle" width="500"  src="https://github.com/Raphaneitor/AdventureWorksPortfolio/blob/main/imagens/Medidas/Cost%20%25.png?raw=true">

🔸<b>Cost %: </b>Mostra a taxa de crescimento ou redução dos custos.<br>

<img align="middle" width="500"  src="https://github.com/Raphaneitor/AdventureWorksPortfolio/blob/main/imagens/Medidas/Cost%20LY.png?raw=true">

🔸<b>Cost LY (custo do ano anterior):</b> Ajuda a identificar o total dos custos com o mesmo período do ano anterior.<br>

<img align="middle" width="500"  src="https://github.com/Raphaneitor/AdventureWorksPortfolio/blob/main/imagens/Medidas/Cost%20LY%20Delta.png?raw=true">

🔸<b>Cost LY Delta: </b>Mostra em valores a diferença de custos de um ano para o outro.<br>

<img align="middle" width="500"  src="https://github.com/Raphaneitor/AdventureWorksPortfolio/blob/main/imagens/Medidas/Cost%20LY%20Delta%20%25.png?raw=true">

🔸<b>Cost LY Delta %: </b>Mostra em forma de porcentagem a diferença de valores de custo de um ano para o outro.<br>

<img align="middle" width="500"  src="https://github.com/Raphaneitor/AdventureWorksPortfolio/blob/main/imagens/Medidas/Cost%20delta%20%25%20txt.png?raw=true">

🔸<b>Sales Delta % txt: </b>medida com formatação pré-estabelecida para mostrar em forma de texto a % da diferença de valores de custo entre um período com o outro.<br>

<img align="middle" width="500"  src="https://github.com/Raphaneitor/AdventureWorksPortfolio/blob/main/imagens/Medidas/Gross%20Margin.png?raw=true">

🔸<b>Gross Margin: </b>Serve para mostrar o total de margem bruta da empresa em relação as vendas<br>

<img align="middle" width="500"  src="https://github.com/Raphaneitor/AdventureWorksPortfolio/blob/main/imagens/Medidas/Gross%20Margin%20%25.png?raw=true">

🔸<b>Gross Margin %: </b>Mostra a taxa de crescimento ou redução na margem de lucro da empresa.<br>

<img align="middle" width="500"  src="https://github.com/Raphaneitor/AdventureWorksPortfolio/blob/main/imagens/Medidas/Gross%20Margin%20LY.png?raw=true">

🔸<b>Gross Margin LY:</b> Ajuda a identificar o total de margem bruta com o mesmo período do ano anterior.<br>

<img align="middle" width="500"  src="https://github.com/Raphaneitor/AdventureWorksPortfolio/blob/main/imagens/Medidas/Gross%20Margin%20LY%20Delta%20.png?raw=true">

🔸<b>Gross Margin LY Delta: </b>Mostra em valores a diferença de margem bruta de um ano para o outro.<br>

<img align="middle" width="500"  src="https://github.com/Raphaneitor/AdventureWorksPortfolio/blob/main/imagens/Medidas/Gross%20Margin%20LY%20Delta%20%25.png?raw=true">

🔸<b>Gross Margin LY Delta %:</b> Mostra em forma de porcentagem a diferença de valores de margem bruta de um ano para o outro.<br>

<img align="middle" width="500"  src="https://github.com/Raphaneitor/AdventureWorksPortfolio/blob/main/imagens/Medidas/Gross%20Margin%20Delta%20%25%20txt.png?raw=true">

🔸<b>Gross Margin Delta % txt:</b> medida com formatação pré-estabelecida para mostrar em forma de texto a % da diferença de valores de margem bruta entre um período com o outro.<br>

<img align="middle" width="500"  src="https://github.com/Raphaneitor/AdventureWorksPortfolio/blob/main/imagens/Medidas/Sales%20Quantity.png?raw=true">

🔸<b>Sales Quantity:</b> Serve para mostrar o total de vendas realizadas.<br>

<img align="middle" width="500"  src="https://github.com/Raphaneitor/AdventureWorksPortfolio/blob/main/imagens/Medidas/Sales%20Quantity%20LY%20.png?raw=true">

🔸<b>Sales Quantity LY (quantidade de vendas do ano passado):</b> Ajuda a identificar o total de vendas realizadas com o mesmo período do ano anterior.<br>  

<img align="middle" width="500"  src="https://github.com/Raphaneitor/AdventureWorksPortfolio/blob/main/imagens/Medidas/Sales%20Quantity%20LY%20Delta.png?raw=true">

🔸<b>Sales Quantity LY Delta:</b> Mostra em valores a diferença de vendas realizadas de um ano para o outro.<br>

<img align="middle" width="500"  src="https://github.com/Raphaneitor/AdventureWorksPortfolio/blob/main/imagens/Medidas/Sales%20Quantity%20LY%20Delta%20%25.png?raw=true">

🔸<b>Sales Quantity LY Delta %: </b>Mostra em forma de porcentagem a diferença de valores de venda realizada de um ano para o outro.<br>

<img align="middle" width="500"  src="https://github.com/Raphaneitor/AdventureWorksPortfolio/blob/main/imagens/Medidas/Sales%20Quantity%20Delta%20%25%20txt.png?raw=true">

🔸<b>Sales Quantity Delta % txt:</b> medida com formatação pré-estabelecida para mostrar em forma de texto a % da diferença de valores de quantidade de vendas entre um período com o outro.<br>

<img align="middle" width="500"  src="https://github.com/Raphaneitor/AdventureWorksPortfolio/blob/main/imagens/Medidas/Discount.png?raw=true">

🔸<b>Discount:</b>Ajuda a identificar os valores de desconto nas vendas pela empresa em um período.<br>

<img align="middle" width="500"  src="https://github.com/Raphaneitor/AdventureWorksPortfolio/blob/main/imagens/Medidas/Sales%20Last%20Date.png?raw=true">

🔸<b>Sales Last Date:</b> medida utilizada para mostrar a data da ultima venda de um determinado período.<br>

<img align="middle" width="500"  src="https://github.com/Raphaneitor/AdventureWorksPortfolio/blob/main/imagens/Medidas/Sales%20Year%20to%20Date.png?raw=true">

🔸<b>Sales Year to Date:</b> Serve para acompanhar o desempenho de vendas ao longo do ano, ajudando a analisar se a empresa está cumprindo suas metas de vendas anuais/mensais.<br>

<img align="middle" width="500"  src="https://github.com/Raphaneitor/AdventureWorksPortfolio/blob/main/imagens/Medidas/Sales%20Year%20to%20Date%20Last%20Year.png?raw=true">

🔸<b>Sales Year to Date Last Year:</b> Utilizada para medir o desempenho de vendas ao longo do ano em relação ao ano anterior e observar tendências de crescimento ou declínio.<br>
Após todas as nossas medidas criadas, podemos partir para a elaboração do dashboard, criando todas as nossas analises constando principalmente comparações em relação a períodos de tempo, como no ultimo ano principalmente, e a partir daí, analisar por meio do volume/quantidade de vendas, como está o desempenho da empresa com base nas informações que possuímos.
<br><br>
## 🔷Dashboard e Insights
<img align="middle" width="800"  src="https://github.com/Raphaneitor/AdventureWorksPortfolio/blob/main/imagens/AdventureWorks_neon_Dashboard_Overview.png?raw=true">
<img align="middle" width="800"  src="https://github.com/Raphaneitor/AdventureWorksPortfolio/blob/main/imagens/AdventureWorks_neon_Dashboard_Detail.png?raw=true"><br>
Através da criação de todas as medidas e elaboração do dashboard, podemos com base nas seleções que fizermos no dashboard para pontos mais específicos, verificar as situações com base em cada categoria, porem para uma análise de insights para essa tela padrão, podemos verificar que:<br><br>
🔺Mais de 96% das vendas e lucro da empresa se concentram em apenas 1 tipo de produto e em 3 tipos de subcategorias desse mesmo produto, fazendo com que ele seja extremamente dependente dessa linha e assim podendo gerar problemas financeiros para a mesma pois ela n tem formas de diversificar os seus lucros e caso tenha algum problema com esse tipo de produto, ela terá um impacto financeiro significativo. Uma forma de contornar esse problema seria o incentivo de vendas para as outras categorias de produtos (roupas e acessórios) por meio de promoções das mesmas.<br><br>
🔺Mais da metade das vendas são realizadas nos países dos EUA e Australia, e caso queira diversificar o seu mercado, é recomendado que faça campanhas de marketing e/ou promoções/desconto nas outras localidades de venda significativa como é no caso a Europa e o Canadá.<br><br>
🔺O número de vendas cai consideravelmente no começo do ano, e sendo assim, poderia ser criado campanhas de marketing e/ou promoções/descontos sazonais nesse período, sendo eles o primeiro/segundo trimestre do ano.<br><br>

## 🔷Elementos do Dashboard
Essa é apenas uma analise preliminar através da base do dashboard desenvolvido, porem vale ressaltar quais os tipos de elementos da ferramenta utilizamos na confecção do relatório, e eles são:<br><br>
🔸<b>Card de quantidade de vendas:</b> Serve para destacar o total de vendas realizadas com base nos dados disponibilizados.<br><br>
🔸<b>Card de vendas:</b> Serve para destacar o valor total arrecadado para as vendas.<br><br>
🔸<b>Card de custos:</b> Serve para destacar e monitorar os custos sumarizados até a realização da venda.<br><br>
🔸<b>Card de Margem de lucro bruto:</b> Serve para avaliar a rentabilidade da empresa, combinando vendas e custos.<br><br>
🔸<b>Tipo de Produto (gráfico de rosca):</b> Mostra quais os principais tipos de produtos vendem na Empresa. No caso do Adventure Works, na maior parte do tempo, mais de 96% das vendas são de bicicletas.<br><br>
🔸<b>Vendas por país (gráfico de funil):</b> Serve para identificar os países como o maior número de vendas, permitindo analises geográficas. Os EUA, juntamente da Australia, lideram as vendas por uma boa margem em relação aos outros países.<br><br>
🔸<b>Vendas por Subcategoria de produtos (gráfico de colunas):</b> Indica as TOP 3 subcategorias de produtos que tem maior impacto nas vendas.<br><br>
🔸<b>Venda por mês (gráfico de colunas):</b> Serve para demonstrar a quantidade de vendas por mês ao longo do período de um ano. <br><br>
🔸<b>Vendas acumuladas (gráfico de linhas):</b> Serve para comparar o desempenho de vendas do ano atual com o ano anterior, de forma acumulada, ajudando a verificar comparações de como estavam as vendas acumuladas até um determinado período do ano. <br><br>
🔸<b>Filtros (anos e menu lateral):</b> Permitem personalizar as visualizações por meio de diversas categorias de dados.<br><br>
🔸<b>Tooltips (detalhamento):</b> Oferecem informações adicionais ao passar o cursor pelos elementos gráficos do dashboard.<br><br>
🔸<b>Drill-through (tabela de detalhe das vendas):</b> Oferecem informações detalhadas ao selecionar qualquer medida com o botão direito e selecionar o Drill-through para o dashboard de vendas online detalhes, deixando as analises muito mais profundas.
<br><br>
## 🔷Considerações finais
Através desse projeto, podemos utilizar os dados que estavam armazenados de forma Bruta para realizar sua modelagem, visualização e geração de insights de negócio, que no caso da Empresa Adventure Works, falando de forma preliminar, precisaria diversificar os seus lucros e investir em outras localidades/períodos para que tenha uma rentabilidade mais estável.

## Ferramentas e linguagens utilizadas
<div style="display: inline_block">
    <img align="center" alt="SQL" height="40" width="40" src="https://github.com/Raphaneitor/Portfolio/blob/main/linguagens/sql.png?raw=true">
    <img align="center" alt="Power BI" height="40" width="40" src="https://github.com/Raphaneitor/Portfolio/blob/main/linguagens/power%20bi.png?raw=true">
</div>
