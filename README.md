## Análise da SuperStore RFM & Cohort & Descriptive

# Problema de Negócio

### A SuperStore é uma rede de supermercados com várias unidades físicas espalhadas por todo o mundo, com o objetivo de fornecer alimentos e comercializar os mais diversos produtos para consumo.

O time de gerentes da Superstore decidiu construir uma área de dados para facilitar as decisões da empresa relacionadas ao abastecimento de produtos das lojas e às vendas.

Atualmente, os gerentes têm acesso a algumas planilhas com informações pontuais que auxiliam na tomada de decisão. No entanto, eles gostariam que todos os dados da empresa fossem integrados, de modo que cada área pudesse acompanhar os mesmos indicadores e utilizar uma fonte única de informação.

O time de dados desempenhará um papel importante na criação desses indicadores, pois terá acesso aos dados transacionais da empresa para analisar o comportamento dos clientes. Entre as análises que poderão ser realizadas estão a identificação dos produtos mais comprados, a quantidade adquirida, o tamanho médio da cesta de compras, o valor médio gasto por compra, os produtos devolvidos, o número de pedidos realizados em determinado período e diversos outros indicadores relevantes para o negócio.

# Premissas da análise

Dados de 9.994 vendas feitas pela SuperStore.

Vendas realizadas nos Estados Unidos.

Os dados analisados correspondem ao período de 2014 a 2018.

# Estratégia da solução

O método Fato-Dimensão foi usado para desenvolver a análise de dados.



# Analise Descritiva
# Passo 1: Resumir o contexto em uma pergunta aberta

As perguntas abertas são um tipo de demanda muito comum em análise de dados nas quais a demanda possui N possíveis soluções e cabe ao analista de dados avaliar as possibilidades e escolher a alternativa com o maior retorno e o menor esforço possível. Para essa análise, foi definida a seguinte pergunta aberta:

Como estão as vendas da SuperStore? a empresa esta dando lucro? a um crescimento no nmr de clientes e compras ao longo do tempo?

# Passo 2: Transformar pergunta aberta em fechada

As perguntas fechadas são um tipo de demanda muito comum na área de análise de dados. Essa demanda contém todos os detalhes da análise de dados e direciona o analista exatamente para o que precisa ser feito. Geralmente, a pergunta fechada é a escolha de uma solução entre todas as alternativas possíveis, feita por um profissional mais sênior da área.

Para essa análise, foi definida a seguinte pergunta fechada:

Pergunta Fechada: faca uma analise das vendas da superstore, veja qual categoria esta dentro da lei de pareto, (80-20) como estao o nmr de clientes, o nmr de pedidos, ele esta aumentando? estagnou? quais categorias nao trazem retorno para a superstore? faca a analise com o grafico de pareto

# Passo 3: Definição da Coluna Fato

O Fato é a coluna de interesse que representa o ponto focal da análise. Nesse caso, a coluna "OrderID" mostra quantas vendas foram feitas, quando, é feita uma contagem i e feito uma segmentação por categoria...

# Passo 4: Identificação das Dimensões

As colunas foram agrupadas em dimensões comuns que fornecem mais detalhes sobre o Fato que será analisado. Foram organizadas as seguintes dimensões:


Tempo (Datas do Pedido e Envio)	Order Date, Ship Date
(a partir delas, pode-se extrair: order_year, order_month, order_quarter, ship_year, ship_month)

Cliente (Quem Comprou)	Customer ID, Customer Name, Segment, Country, City, State, Postal Code, Region

Produto (O que Foi Vendido)	Product ID, Category, Sub-Category, Product Name

Pedido (Cabeçalho da Transação)	Order ID, Ship Mode (modo de frete/entrega)

Item do Pedido (Linha/Detalhe do Fato)	Row ID (identificador único de cada linha do pedido), Sales (valor da venda), Quantity (quantidade), Discount (desconto aplicado), Profit (lucro)

# Passo 5: Combinação Fato-Dimensão  

Mind Map – Direcionadores de Análise

Para orientar a exploração dos dados, mesmo sendo um analista novo no setor, foram mapeados os seguintes grupos de perguntas:

Quantidade de Pedidos por Data(Mes)

Quantidade de Pedidos por Data de Envio(Mes)

Quantidade de Pedidos por Tier de Preço (Baixo, Médio, Alto)

Quantidade de Pedidos por Quantidade de Itens

Quantidade de Pedidos por Tier de Desconto (Baixo, Médio, Alto)

Quantidade de Pedidos por Produto

Quantidade de Pedidos por Clientes

Quantidade de Pedidos por Data e Tier de Preço (Baixo, Médio, Alto)

Quantidade de Pedidos por Data e Quantidade de Itens

Quantidade de Pedidos por Data e Produto

Quantidade de Pedidos por Data e Clientes

Quantidade de Pedidos por Data de Envio e Tier de Preço

# Passo 6: Escolha dos Gráficos 
- [x]  Quantidade de Pedidos por Data (Mes) Gráfico de Linhas
 
- [x]  Desenhar o gráfico de Quantidade de Clientes Únicos

- [x]  Quantidade Pedidos por Cliente

- [x]  Quantidade de Pedidos por Itens

- [x]  Desenhar o gráfico de Distr. Pedidos por produto

# Passo 7: Painel Macro-Micro
https://img.notionusercontent.com/s3/prod-files-secure%2F2b76fb90-3276-8107-9a2b-0003db8f3f1b%2F559e753e-ca94-4d58-97e5-2cf9018ed757%2FCapturar.png/size/w=2000?exp=1782695552&sig=WhAahVMGwk-4q-j_K8-f3v_bZCRHuSz-Lx-xrUz4v6k&imgBuildSrc=presignImageUrl&id=38e6fb90-3276-8076-b420-e1499e5d1c32&table=block&userId=2cdd872b-594c-8197-aa3d-0002004cefb4&mtd=com

# Insights da análise

# Resultados

**📥 Baixe a apresentação em PowerPoint (clique no link e, em seguida, em "Download" ou "View raw"):**  
  [https://docs.google.com/presentation/d/1NhQ-8F8iABrALSBeC_FBwQPg6H6-_DK8/edit?usp=sharing&ouid=114029927907630112086&rtpof=true&sd=true](https://docs.google.com/presentation/d/1NhQ-8F8iABrALSBeC_FBwQPg6H6-_DK8/edit?usp=sharing&ouid=114029927907630112086&rtpof=true&sd=true)

# Próximos passos

Entrar em contato com o engenheiro de dados para entender as fontes de dados da empresa e verificar se os dados coletados estão íntegros e consistentes.

Realizar uma auditoria na base de dados para identificar possíveis falhas de coleta, processamento, integração ou modelagem que possam estar comprometendo as análises.

Comunicar o CEO e a gerência sobre os problemas identificados, destacando que os dados atuais podem não refletir a realidade do negócio.

Recomendar que decisões estratégicas relevantes, como expansão, investimentos ou mudanças operacionais significativas, não sejam tomadas com base na base de dados atual até que sua qualidade e confiabilidade sejam validadas.
