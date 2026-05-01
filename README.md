# 📊 Projeto de Análise de Churn: Retenção de Clientes Bancários

Este projeto utiliza **Python** e a biblioteca **Pandas** para investigar padrões que levam ao cancelamento de cartões de crédito.

## 🚀 Tecnologias Utilizadas
* **Python**
* **Pandas**
* **Plotly**

---

## 🛠️ Metodologia e Processamento de Dados

### 1. Importação e Leitura
O arquivo foi carregado utilizando o encoding `latin1` para suportar caracteres especiais.

* **Comando:** `pd.read_csv('Dados_bancarios.csv', encoding='latin1')`

![Leitura de Dados](imagens/import_pandas_as_pd.png)

### 2. Auditoria da Base
Verificamos o tamanho da base e a existência de valores nulos para garantir a qualidade da análise.

![Shape](imagens/df_shape.png)
![Null Values](imagens/df_isnull.png)

### 3. Segmentação de Grupos
Separei os clientes entre ativos e cancelados para comparar comportamentos médios.

![Segmentação](imagens/df_cancelados_+_df_ativos.png)

### 4. Tratamento de Erros e Correção Lógica
Identificamos que cálculos matemáticos devem ser feitos sobre valores brutos (`.shape[0]`), evitando erros de lógica com tabelas inteiras.

![Erro de Lógica](imagens/erro%20NaN.png)
![Correção](imagens/shape[0]_corrigido.png)

---

## 🔍 Principais Insights Extraídos

1. **A Regra dos 4 Produtos:** Clientes com 4+ produtos têm maior retenção.
2. **Gargalo no Platinum:** Maior taxa de churn identificada nesta categoria.
3. **Engajamento:** Clientes que cancelam usam apenas 16% do limite.

---

## 📈 Visualização de Resultados

### Comparativo por Categoria de Cartão
![Gráfico de Cartões](imagens/grafico_catergoria_cartao.png)

### Relação Limite vs Consumo
![Gráfico de Dispersão](imagens/grafico_limite_cartao.png)
