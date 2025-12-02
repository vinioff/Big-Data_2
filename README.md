# Previsão de Demanda de Aluguel de Bicicletas

Este projeto desenvolve um modelo de machine learning para prever a quantidade de bicicletas alugadas diariamente em uma startup de locação em áreas praianas. O foco é otimizar o cronograma de manutenção, evitando retirar equipamentos em dias de alta demanda, com base em fatores como clima, estação do ano e tipo de dia.

## Objetivo
Criar uma ferramenta preditiva que estime o número de locações diárias, ajudando a empresa a planejar manutenções em períodos de baixa demanda, reduzindo reclamações de clientes e melhorando a eficiência operacional.

## Dados
Os dados vêm do arquivo `bike_rev_1.csv`, que inclui:
- **Estação do ano** (primavera, verão, outono, inverno)
- **Ano** (2018 ou 2019)
- **Mês** (1 a 12)
- **Feriado** (sim/não)
- **Dia da semana** (0 a 6)
- **Dia útil** (sim/não)
- **Condição climática** (de 1 a 4, variando de claro a chuva forte/neve)
- **Temperatura** (real e aparente, em Celsius)
- **Umidade** e **velocidade do vento**
- **Aluguéis totais** (variável alvo: cnt)

O dataset cobre locações históricas para treinamento e teste.

## Metodologia
1. **Análise Exploratória**: Verificação de tipos de dados, correção de valores nulos, métricas estatísticas e visualizações para entender padrões (ex.: demanda maior em dias quentes e ensolarados).
2. **Pré-processamento**: Conversão de variáveis categóricas (como estação) via One-Hot Encoding. Normalização dos dados numéricos com MinMaxScaler. Divisão em treino/teste (70/30).
3. **Otimização de Hiperparâmetros**: Uso de GridSearchCV para tunar parâmetros em modelos como Decision Tree, Random Forest e Gradient Boosting.
4. **Treinamento de Modelos**: 
   - Decision Tree Regressor
   - Random Forest Regressor
   - Gradient Boosting Regressor
5. **Avaliação**: Métricas como MSE (Erro Quadrático Médio), MAE (Erro Absoluto Médio) e R² para comparar desempenho.

## Resultados
- **Decision Tree**: MSE ≈ 667k, MAE ≈ 596, R² ≈ 0.82
- **Random Forest**: MSE ≈ 456k, MAE ≈ 463, R² ≈ 0.88
- **Gradient Boosting**: MSE ≈ 378k, MAE ≈ 431, R² ≈ 0.90

O Gradient Boosting se destacou com os menores erros e maior R², tornando-o o mais preciso para prever locações.

## Como Executar
1. Clone o repositório: `git clone https://github.com/vinioff/Big-Data_2.git`
2. Instale dependências: `pip install -r requirements.txt` (inclui pandas, scikit-learn, matplotlib, etc.)
3. Rode o notebook: `jupyter notebook BiG_Data_2.ipynb`
4. Baixe o dataset via Google Drive ID no código (ou forneça localmente).

## Conclusão
Este modelo ajuda a startup a equilibrar manutenção e disponibilidade de bicicletas, melhorando a satisfação do cliente. Futuras melhorias podem incluir dados em tempo real de clima ou integração com APIs para previsões diárias.
