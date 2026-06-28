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

# Passo 1: Resumir o contexto em uma pergunta aberta

As perguntas abertas são um tipo de demanda muito comum em análise de dados nas quais a demanda possui N possíveis soluções e cabe ao analista de dados avaliar as possibilidades e escolher a alternativa com o maior retorno e o menor esforço possível. Para essa análise, foi definida a seguinte pergunta aberta:

Como estão as vendas da Amazon? A empresa tem muitos produtos bons ou é simplesmente um armazém de brechó?

# Passo 2: Transformar pergunta aberta em fechada

As perguntas fechadas são um tipo de demanda muito comum na área de análise de dados. Essa demanda contém todos os detalhes da análise de dados e direciona o analista exatamente para o que precisa ser feito. Geralmente, a pergunta fechada é a escolha de uma solução entre todas as alternativas possíveis, feita por um profissional mais sênior da área.

Para essa análise, foi definida a seguinte pergunta fechada:

Pergunta Fechada: Faça um gráfico de Pareto mostrando todas as categorias da Amazon. Veja quais categorias pagam as contas da empresa e quais são simplesmente peso morto no estoque.

# Passo 3: Definição da Coluna Fato

O Fato é a coluna de interesse que representa o ponto focal da análise. Nesse caso, a coluna "OrderID" mostra quantas vendas foram feitas, quando, e é feita uma contagem e segmentação por categoria...

# Passo 4: Identificação das Dimensões

As colunas foram agrupadas em dimensões comuns que fornecem mais detalhes sobre o Fato que será analisado. Foram organizadas as seguintes dimensões:

**Tempo:** OrderDate. (Base cronológica para análises de sazonalidade e tendências).

**Produto e Marca:** ProductID, ProductName, Category, Brand. (Detalhamento do item vendido para análise de portfólio e desempenho por categoria).

**Cliente e Vendedor:** CustomerID, CustomerName, SellerID. (Identificação das partes envolvidas na transação).

**Valores e Custos:** Quantity, UnitPrice, Discount, Tax, ShippingCost, TotalAmount. (Métricas financeiras da venda; TotalAmount é a métrica central de faturamento).

**Pagamento e Status:** PaymentMethod, OrderStatus. (OrderStatus é a variável-alvo para classificação do resultado do pedido).

**Localização:** City, State, Country. (Base geográfica para análises regionais de desempenho).

**Controle:** OrderID. (Identificador único para rastreabilidade do registro).

# Passo 5: Hipóteses Analíticas

**H1:** Não existe a Lei de Pareto na Amazon. As categorias vendem de forma relativamente equilibrada.

**H2:** Apenas duas categorias não apresentam vendas. As demais vendem de forma uniforme.

**H3:** O faturamento por categoria é baixo na maior parte das categorias, mostrando que as receitas estão distribuídas entre diversos segmentos.

**H4:** O lucro de muitas categorias é negativo, indicando que os custos de tráfego e aquisição de clientes superam o ganho obtido por venda.

H5: quais marcas tiveram maior participação nas vendas?

Fiz no início apenas 4 Hipóteses para quebrar o gelo. Isso é uma análise exploratória do dataframe com base na pergunta fechada que o Analista de Dados Sr. (Gustavo Shelby) me sugeriu.

**Hipótese Inicial → Rodar Excel/Análise → Obter Insight → Questionar o Insight → Gerar Nova Hipótese → Rodar Nova Análise.**

# Passo 6: Critérios de Priorização

- **Critério 1:** Dados disponíveis.
- **Critério 2:** Insights acionáveis.

# Passo 7: Priorização das Hipóteses Analíticas

**H1:** Não existe a Lei de Pareto na Amazon. As categorias vendem de forma relativamente equilibrada.

**H2:** Apenas duas categorias não apresentam vendas. As demais vendem de forma uniforme.

**H3:** O faturamento por categoria é baixo na maior parte das categorias, mostrando que as receitas estão distribuídas entre diversos segmentos.

**H4:** O lucro de muitas categorias é negativo, indicando que os custos de tráfego e aquisição de clientes superam o ganho obtido por venda.

H5: quais marcas tiveram maior participação nas vendas?

# Insights da análise

# Resultados

**📥 Baixe a apresentação em PowerPoint (clique no link e, em seguida, em "Download" ou "View raw"):**  
  [https://docs.google.com/presentation/d/1NhQ-8F8iABrALSBeC_FBwQPg6H6-_DK8/edit?usp=sharing&ouid=114029927907630112086&rtpof=true&sd=true](https://docs.google.com/presentation/d/1NhQ-8F8iABrALSBeC_FBwQPg6H6-_DK8/edit?usp=sharing&ouid=114029927907630112086&rtpof=true&sd=true)

# Próximos passos

Entrar em contato com o engenheiro de dados para entender as fontes de dados da empresa e verificar se os dados coletados estão íntegros e consistentes.

Realizar uma auditoria na base de dados para identificar possíveis falhas de coleta, processamento, integração ou modelagem que possam estar comprometendo as análises.

Comunicar o CEO e a gerência sobre os problemas identificados, destacando que os dados atuais podem não refletir a realidade do negócio.

Recomendar que decisões estratégicas relevantes, como expansão, investimentos ou mudanças operacionais significativas, não sejam tomadas com base na base de dados atual até que sua qualidade e confiabilidade sejam validadas.
