# 📊 Análise de Churn: Por que os clientes cancelam o cartão?

Este projeto analisa uma base de dados de 10.000 clientes bancários para identificar padrões que levam ao cancelamento (Churn).

## 🚀 Tecnologias Utilizadas
* Python
* Pandas (Tratamento de dados)
* Plotly (Visualização interativa)

## 🔍 Principais Insights Extraídos
Após a análise técnica, identificamos quatro pontos críticos:

1. **A Regra dos 4 Produtos:** Clientes com 4 ou mais produtos têm uma taxa de retenção drasticamente maior. A média de produtos de quem fica é **3.91**, enquanto quem sai tem média **3.28**.
2. **Gargalo no Cartão Platinum:** 25% dos clientes Platinum cancelam a conta, a maior taxa entre todas as categorias.
3. **Sinal de Esfriamento:** Clientes que cancelam usam apenas **16%** do limite disponível, contra **30%** dos ativos. O desengajamento acontece meses antes do cancelamento oficial.
4. **Comunicação Ativa:** O número de contatos com o banco é maior nos clientes que cancelam (2.97 vs 2.36), sugerindo que eles tentam resolver problemas antes de desistir.

## 📈 Como rodar o projeto
1. Clone o repositório
2. Instale as dependências: `pip install pandas plotly`
3. Execute o arquivo `analise.py`
