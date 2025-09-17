# 📊 Predição de Preços de Imóveis com Machine Learning

## 📝 Descrição
Este projeto tem como objetivo prever o preço de imóveis a partir de diferentes variáveis (metragem, localização, número de quartos, etc.).  
Foram aplicadas técnicas de **análise exploratória, tratamento de dados, engenharia de atributos e comparação de múltiplos modelos de Machine Learning**.  

---

## 📂 Estrutura do Projeto
- **`MainProject.ipynb`** → Notebook principal com todo o fluxo do projeto.  
- **`data/`** → Pasta para armazenar o dataset bruto e processado (não é obrigatório subir no GitHub se os dados forem muito grandes).  
- **`models/`** → Modelos salvos em `.pkl` para reutilização.  
- **`README.md`** → Descrição do projeto.  

---

## ⚙️ Tecnologias Utilizadas
- Python 3.11  
- Pandas, NumPy  
- Matplotlib, Seaborn, Plotly  
- Scikit-learn  
- Scipy  
- Statsmodels  
- Joblib  

---

## 📊 Etapas do Projeto
1. **Análise Exploratória**  
   - Verificação de valores nulos, inconsistentes e outliers.  
   - Visualizações de distribuições e correlações.  

2. **Pré-processamento**  
   - Tratamento e remoção de outliers.   
   - Normalização/Padronização de variáveis numéricas (`StandardScaler`).  

3. **Modelagem**  
   - Modelos testados:  
     - Decision Tree
     - Knn 
     - Random Forest Regressor  
     - Support Vector Regressor (SVR)  
     - Rede Neural (MLP)  
     - Linear Regression 
     - GradientBoostingRegressor
   - Ajuste de hiperparâmetros com `GridSearchCV` e `RandomizedSearchCV`.  

4. **Comparação de Modelos**  
   - Métricas utilizadas:  
     Para comparar os modelos de forma justa, utilizei o método **MultiComparison** da biblioteca `statsmodels`.  
      Esse método permite realizar testes estatísticos (ex: Tukey HSD) para verificar se as diferenças de desempenho entre os modelos são **estatisticamente significativas** e não apenas resultado de variações aleatórias.
   - Testes feitos com **dados originais** e **dados tratados sem outliers**.  

5. **Resultados**  
   - Tabela comparativa destacando o melhor modelo.  
   - Conclusão sobre o impacto do tratamento de outliers no desempenho.  

6. **Deploy Local**  
   - Modelo vencedor salvo em `.pkl` com `joblib`.  
   - Pode ser carregado em outros projetos ou APIs para previsão.  

---

## 🚀 Como Rodar
1. Clone este repositório:  
   ```bash
   git clone https://github.com/PedroHenriqueBRO/HousePrediction-ML-Models.git #para HTTPS
   git clone git@github.com:PedroHenriqueBRO/HousePrediction-ML-Models.git #para SSH
   cd HousePrediction-ML-Models
   ```
2. Crie um ambiente virtual e instale as dependências:  
   ```bash
   pip install -r requirements.txt
   ```
3. Abra o notebook:  
   ```bash
   jupyter notebook MainProject.ipynb
   ```
4. Para carregar o modelo final:  
   ```python
   import joblib
   modelo = joblib.load("models/MelhorModelo(GBR).pkl")
   previsao = modelo.predict(novos_dados)
   ```

---

## 📈 Resultados Finais
- Melhor modelo: **[GBR]**  
- Quando treinado diretamente com a base de dados com ruído e utilizando o score sobre esses mesmos dados ele apresenta score de 97%.
Já quando colocado para fazer o mesmo processo mas com a base sem ruído ele apresenta score de 68%.
---

## 📌 Conclusão
- O tratamento de outliers impactou diretamente na performance.  
- Comparando diferentes algoritmos, **[GBR]** apresentou o melhor desempenho.  
- O pipeline criado é reaproveitável para novos datasets.  
