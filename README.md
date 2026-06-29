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

# Análise Descritiva

## Passo 1: Resumir o contexto em uma pergunta aberta

As perguntas abertas são um tipo de demanda muito comum em análise de dados nas quais a demanda possui N possíveis soluções e cabe ao analista de dados avaliar as possibilidades e escolher a alternativa com o maior retorno e o menor esforço possível. Para essa análise, foi definida a seguinte pergunta aberta:

Como estão as vendas da SuperStore? A empresa está dando lucro? Há um crescimento no número de clientes e compras ao longo do tempo?

## Passo 2: Transformar pergunta aberta em fechada

As perguntas fechadas são um tipo de demanda muito comum na área de análise de dados. Essa demanda contém todos os detalhes da análise de dados e direciona o analista exatamente para o que precisa ser feito. Geralmente, a pergunta fechada é a escolha de uma solução entre todas as alternativas possíveis, feita por um profissional mais sênior da área.

Para essa análise, foi definida a seguinte pergunta fechada:

**Pergunta Fechada:** Faça uma análise das vendas da Superstore, veja qual categoria está dentro da lei de Pareto (80-20), como estão o número de clientes, o número de pedidos, ele está aumentando? Estagnou? Quais categorias não trazem retorno para a Superstore? Faça a análise com o gráfico de Pareto.

## Passo 3: Definição da Coluna Fato

O Fato é a coluna de interesse que representa o ponto focal da análise. Nesse caso, a coluna "OrderID" mostra quantas vendas foram feitas, quando, é feita uma contagem e feito uma segmentação por categoria...

## Passo 4: Identificação das Dimensões

As colunas foram agrupadas em dimensões comuns que fornecem mais detalhes sobre o Fato que será analisado. Foram organizadas as seguintes dimensões:

| Dimensão | Colunas |
| :--- | :--- |
| Tempo (Datas do Pedido e Envio) | Order Date, Ship Date (a partir delas, pode-se extrair: order_year, order_month, order_quarter, ship_year, ship_month) |
| Cliente (Quem Comprou) | Customer ID, Customer Name, Segment, Country, City, State, Postal Code, Region |
| Produto (O que Foi Vendido) | Product ID, Category, Sub-Category, Product Name |
| Pedido (Cabeçalho da Transação) | Order ID, Ship Mode (modo de frete/entrega) |
| Item do Pedido (Linha/Detalhe do Fato) | Row ID (identificador único de cada linha do pedido), Sales (valor da venda), Quantity (quantidade), Discount (desconto aplicado), Profit (lucro) |

## Passo 5: Combinação Fato-Dimensão

**Mind Map – Direcionadores de Análise**

Para orientar a exploração dos dados, mesmo sendo um analista novo no setor, foram mapeados os seguintes grupos de perguntas:

- Quantidade de Pedidos por Data (Mês)
- Quantidade de Pedidos por Data de Envio (Mês)
- Quantidade de Pedidos por Tier de Preço (Baixo, Médio, Alto)
- Quantidade de Pedidos por Quantidade de Itens
- Quantidade de Pedidos por Tier de Desconto (Baixo, Médio, Alto)
- Quantidade de Pedidos por Produto
- Quantidade de Pedidos por Clientes
- Quantidade de Pedidos por Data e Tier de Preço (Baixo, Médio, Alto)
- Quantidade de Pedidos por Data e Quantidade de Itens
- Quantidade de Pedidos por Data e Produto
- Quantidade de Pedidos por Data e Clientes
- Quantidade de Pedidos por Data de Envio e Tier de Preço

## Passo 6: Escolha dos Gráficos

- [x] Quantidade de Pedidos por Data (Mês) - Gráfico de Linhas
- [x] Desenhar o gráfico de Quantidade de Clientes Únicos
- [x] Quantidade de Pedidos por Cliente
- [x] Quantidade de Pedidos por Itens
- [x] Desenhar o gráfico de Distribuição de Pedidos por Produto

## Passo 7: Painel Macro-Micro

[https://img.notionusercontent.com/s3/prod-files-secure%2F2b76fb90-3276-8107-9a2b-0003db8f3f1b%2F559e753e-ca94-4d58-97e5-2cf9018ed757%2FCapturar.png/size/w=2000?exp=1782695552&sig=WhAahVMGwk-4q-j_K8-f3v_bZCRHuSz-Lx-xrUz4v6k&imgBuildSrc=presignImageUrl&id=38e6fb90-3276-8076-b420-e1499e5d1c32&table=block&userId=2cdd872b-594c-8197-aa3d-0002004cefb4&mtd=com](https://img.notionusercontent.com/s3/prod-files-secure%2F2b76fb90-3276-8107-9a2b-0003db8f3f1b%2F559e753e-ca94-4d58-97e5-2cf9018ed757%2FCapturar.png/size/w=2000?exp=1782695552&sig=WhAahVMGwk-4q-j_K8-f3v_bZCRHuSz-Lx-xrUz4v6k&imgBuildSrc=presignImageUrl&id=38e6fb90-3276-8076-b420-e1499e5d1c32&table=block&userId=2cdd872b-594c-8197-aa3d-0002004cefb4&mtd=com)

# Análise de Cohort & RFM

A parte de estruturação foi baseada na metodologia do Meigarom Lopes (Data Scientist Sr.). Foi usado para a matriz de RFM a estrutura criada pela G4 Educação, utilizando os grupos e a forma que ela segmenta os clientes por recência, monetização e frequência.

## 1. O grande mal-entendido do Churn

**O dado:** 89% dos clientes somem no 1º mês.

**O que realmente significa:** Você NÃO perdeu esses clientes. Eles não compram todo mês porque não são viciados em comprar da sua loja. Eles compram quando precisam (ex: material de construção, matrícula escolar, insumos industriais). A coorte prova isso: eles somem, mas voltam em ondas nos meses 11, 17 e 22 (ciclos de ~6 meses).

**Conclusão direta:** Você está gastando dinheiro tentando reativar alguém em 60 dias, mas os dados mostram que eles só querem ser perturbados de 6 em 6 meses. Pare de tratar cliente sazonal como cliente recorrente.

## 2. O Dono do Dinheiro (Quem paga suas contas)

**O dado:** "Campeões" geraram R$ 969 milhões. "Risco" gerou R$ 5,97 bilhões. "Fies" gerou R$ 6,16 bilhões.

**O que realmente significa:** Seus Campeões (clientes perfeitos) são uma ilusão bonitinha, mas representam apenas 5,5% da receita. Quem realmente coloca dinheiro no caixa são os clientes "Risco" e "Fies" – juntos, eles são 70% de todo o seu faturamento.

**Conclusão direta:** Você está tratando os "Campeões" como reis, mas os "Risco" e "Fies" são os plebeus que pagam o castelo. Seu time de marketing precisa parar de mimar os 5% e começar a abraçar os 70%.

## 3. A Grande Contradição (O nome "Risco" está te enganando)

**O dado:** Pela matriz RFM, "Risco" significa: Cliente que comprou há pouco tempo (Recência 1 ou 2) mas comprou poucas vezes (Frequência 3 ou 4).

**O que realmente significa:** Esse cliente é seu MAIOR TESOURO. Ele acabou de comprar, gastou muito (pois gerou R$ 6 bi) e, segundo a coorte, ele vai sumir por alguns meses, mas vai voltar no pico do mês 11 ou 17. Ele não está em "Risco de abandono"; ele está no modo de espera natural do ciclo de compra.

**Conclusão direta:** Mude o nome desse segmento no seu relatório. Chame de "Clientes Sazonais de Alto Valor". A estratégia para eles não é "reativação com desconto", mas sim "Programa de Relacionamento Pós-Venda" para garantir que, quando ele precisar comprar de novo daqui a 6 meses, ele se lembre de você.

## 4. O Horário Certo para Atacar (A Sazonalidade não é aleatória)

**O dado:** Olhe a linha 01-2014. Mês 11 = 22% de recompra. Mês 17 = 13%. Mês 22 = 19%. Já nos meses 2, 5, 7 e 8, a recompra é ZERO ou quase zero.

**O que realmente significa:** Existem "Janelas de Ouro" (meses 11, 17, 22) onde os clientes que sumiram naturalmente lembram de você. E existem "Janelas de Gelo" (meses 2, 5, 8) onde absolutamente ninguém compra de novo, independente do esforço.

**Conclusão direta:**

- Nas janelas de gelo, NÃO gaste verba com reativação. É dinheiro no lixo.
- Nos meses 10, 16 e 21 (um mês antes dos picos), dispare uma enxurrada de e-mail/SMS/WhatsApp. Você vai pegar a onda no momento exato em que o cliente já estava pensando em comprar.

## 5. A Qualidade da Aquisição (Nem todo cliente novo é bom)

**O dado:** Quem entrou em Dezembro/2014 teve 24% de retenção no último mês. Quem entrou em Janeiro/2014 teve apenas 6%.

**O que realmente significa:** Clientes atraídos em épocas de promoção/fim de ano são 4 vezes mais fiéis do que clientes atraídos em Janeiro (mês de ressaca financeira pós-festas).

**Conclusão direta:** Seu time de aquisição está gastando dinheiro em Janeiro para atrair clientes que não valem a pena. Aumente o investimento em Dezembro e reduza drasticamente em Janeiro. O retorno sobre o investimento (ROI) será muito maior.

# Insights da análise

# Resultados

**📥 Baixe a apresentação em PowerPoint (clique no link e, em seguida, em "Download" ou "View raw"):**  
[https://docs.google.com/presentation/d/1NhQ-8F8iABrALSBeC_FBwQPg6H6-_DK8/edit?usp=sharing&ouid=114029927907630112086&rtpof=true&sd=true](https://docs.google.com/presentation/d/1NhQ-8F8iABrALSBeC_FBwQPg6H6-_DK8/edit?usp=sharing&ouid=114029927907630112086&rtpof=true&sd=true)

# Próximos passos

**Passo 1 – Recalcular a segmentação RFM substituindo a coluna "Monetização" pela coluna "Profit" (Lucro):** Os dados atuais de monetização mostram que Risco e Fies faturam R$ 12,13 bi. Porém, o dataset contém a coluna Discount e Profit. É necessário verificar se esses segmentos mantêm a liderança quando a métrica é lucro líquido, ou se os descontos concedidos corroem essa vantagem.

**Passo 2 – Cruzar a lista de produtos/categorias do Pareto (80/20) com os segmentos RFM:** Os dados de vendas estão detalhados por Category e Sub-Category. Deve-se identificar quais categorias estão no topo do Pareto para o segmento "Risco" e quais estão no topo para o segmento "Fies". Se houver divergência, a estratégia de estoque e cross-sell deve ser segmentada por perfil de cliente.

**Passo 3 – Calcular o tempo médio entre compras (intervalo) para os segmentos "Risco" e "Fies":** A coorte mostra picos de recompra nos meses 11, 17 e 22. Deve-se calcular, para cada Customer ID desses segmentos, a mediana dos dias entre uma compra e outra. Se a mediana for consistente com 150-180 dias, a janela de reativação deve ser ajustada para D+150 (e não D+60 ou D+90).

**Passo 4 – Medir o impacto do desconto (Discount) na retenção por coorte:** Os dados contêm a coluna Discount. Deve-se segmentar a coorte de Janeiro/2014 entre clientes que receberam desconto > 15% e clientes com desconto ≤ 5%, e comparar as taxas de recompra no mês 11. Se a taxa for significativamente menor no grupo com alto desconto, a política de descontos deve ser revisada para aquisição de novos clientes.

**Passo 5 – Construir um comparativo de ROI por canal/janela temporal:** Com base nas janelas de gelo (meses 2, 5, 8) e de ouro (meses 10, 16, 21), deve-se calcular o custo médio por contato (e-mail/SMS/WhatsApp) e o retorno médio por cliente reativado em cada período. O período que apresentar maior razão retorno/custo deve receber prioridade orçamentária nos próximos ciclos.
