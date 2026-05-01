📊 Projeto de Análise de Churn: Retenção de Clientes Bancários
Este projeto utiliza Python e a biblioteca Pandas para investigar uma base de dados de 10.000 clientes e descobrir os padrões que levam ao cancelamento de cartões de crédito.

🚀 Tecnologias Utilizadas
Python: Linguagem principal.

Pandas: Manipulação e tratamento de dados.

Plotly: Criação de gráficos interativos para visualização de insights.

🛠️ Metodologia e Processamento de Dados
Abaixo, descrevo o raciocínio lógico aplicado para transformar dados brutos em inteligência de negócio.

1. Importação com Tratamento de Encoding
O primeiro passo foi garantir a leitura correta dos dados. Como o arquivo original possuía caracteres especiais (acentos e símbolos regionais), foi necessário definir o parâmetro de codificação.

Comando: pd.read_csv('Dados_clientes.csv', encoding='latin1')

Aprendizado: Identificar que arquivos gerados pelo Excel no Brasil costumam exigir o padrão latin1 em vez do utf-8.

[COLOQUE O PRINT DA LEITURA DO DATASET E DF.HEAD AQUI]

2. Auditoria e Saneamento da Base
Utilizei ferramentas de diagnóstico para entender a dimensão do projeto e a qualidade dos dados. Verifiquei que a base possui 10.127 linhas e 21 colunas.

Comando: df.shape e df.isnull().sum()

Aprendizado: Validar a integridade da base. Uma base sem valores nulos garante que os cálculos de média e proporção não serão distorcidos.

[COLOQUE O PRINT DO ISNULL.SUM E DO SHAPE AQUI]

3. Segmentação de Grupos (Targeting)
Para descobrir por que os clientes saem, apliquei filtros para isolar os perfis. Essa separação é fundamental para realizar comparações estatísticas precisas entre quem ficou e quem saiu.

Comando: df[df['Categoria'] == 'Cliente'] e df[df['Categoria'] == 'Cancelado']

Lógica: Criar "universos" separados permite comparar, por exemplo, a média de uso de um grupo contra o outro.

[COLOQUE O PRINT DA CRIAÇÃO DAS VARIÁVEIS ATIVOS E CANCELADOS AQUI]

4. Cálculo de Churn e Tratamento de Erros de Lógica
Identificamos uma taxa de cancelamento de 16,07%. Durante esse cálculo, houve um aprendizado importante sobre a estrutura do Pandas.

Desafio: Ao tentar dividir os DataFrames diretamente, o Python retornou valores NaN (Not a Number), pois tentou realizar uma operação entre tabelas inteiras.

Solução: Utilizar o .shape[0] para extrair apenas o valor numérico (quantidade de linhas) necessário para o cálculo matemático.

[COLOQUE O PRINT DO ERRO NAN E DA CORREÇÃO COM .SHAPE[0] AQUI]

🔍 Principais Insights Extraídos
Após o tratamento dos dados, chegamos aos seguintes diagnósticos:

A Regra dos 4 Produtos: Clientes com 4 ou mais produtos contratados dificilmente cancelam. A média de produtos de clientes ativos é 3.91, enquanto a dos cancelados é 3.28.

Gargalo no Cartão Platinum: Este cartão apresenta a maior taxa de churn (25%), indicando que o produto pode não estar competitivo para este público.

Sinal de Esfriamento: Clientes que cancelam usam apenas 16% do limite, contra 30% dos ativos. O desengajamento é visível antes do cancelamento oficial.

Comunicação: O aumento no número de contatos (média de 2.97 nos cancelados) mostra que o cliente tenta resolver problemas antes de desistir.

📈 Visualização de Resultados
[COLOQUE AQUI O PRINT DO GRÁFICO DE BARRAS POR CATEGORIA DE CARTÃO]
Insight: Visualização clara da discrepância de cancelamento no grupo Platinum.

[COLOQUE AQUI O PRINT DO GRÁFICO DE DISPERSÃO (LIMITE VS CONSUMO)]
Insight: Identificação da "linha zero" de consumo entre os clientes que cancelaram.
