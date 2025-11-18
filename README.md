<p align="center">
    <img width="100" src="https://github.githubassets.com/assets/GitHub-Mark-ea2971cee799.png">
</p>

-------

<p align="center">
<img 
    src="https://img.shields.io/badge/ETL-Filmes-4A90E2?style=for-the-badge" /> 
<img src="https://img.shields.io/badge/Python-3.10+-3776AB?style=for-the-badge&logo=python&logoColor=white"/> 
<img src="https://img.shields.io/badge/Pandas-Data%20Processing-150458?style=for-the-badge&logo=pandas"/>
</p>

# 🎬 Projeto ETL de Filmes

> ℹ️ **NOTE:** Este projeto demonstra um fluxo ETL simples, porém completo, utilizando uma base fictícia de filmes, desenvolvido como estudo de boas práticas de Python e Pandas.

O objetivo do projeto é:

- Extrair a base de dados bruta (CSV)  
- Transformar os dados aplicando regras de negócio  
- Carregar o resultado processado em um novo arquivo CSV  

O projeto conta com um **notebook Jupyter** documentando todo o processo de forma didática e prática.

## 📂 Estrutura do Repositório

<p align="center">
<img src="./assets/estrutura.png" width="400"/>
</p>


## 🔍 Fluxo ETL

### 1️⃣ Extract — Leitura da Base Bruta
```python
import pandas as pd

df_raw = pd.read_csv("filmes.csv")
```


### 2️⃣ Transform — Limpeza e Regras de Negócio
- Preenchimento de gêneros vazios com "Not Informed"  
- Classificação por nota: Excellent, Good, Average, No Rating  
- Criação de slug baseado no título 

```python
df_raw['genre'].fillna("Not Informed", inplace=True)
# Exemplo de classificação
def classify_rating(score):
    if score >= 8:
        return "Excellent"
    elif score >= 6:
        return "Good"
    elif score >= 4:
        return "Average"
    else:
        return "No Rating"
df_raw['rating_class'] = df_raw['score'].apply(classify_rating)
```
### 3️⃣ Load — Exportação do Resultado
```python
df_transformed.to_csv("movies_processed.csv", index=False)
```
### ▶️ Como Rodar
- Requisitos
```python
pip install pandas
python etl_movies.ipynb
```

## 👨‍💻 Aluno

<p>
    <img 
      align=left 
      margin=10 
      width=80 
      src="https://avatars.githubusercontent.com/u/174966059?v=4"
    />
    <p>&nbsp&nbsp&nbspFelipe de Lima Passarelli<br>
    &nbsp&nbsp&nbsp
    <a href="https://github.com/Felipe-de-Lima-Passarelli">
    GitHub</a>&nbsp;|&nbsp;
    <a href="https://www.linkedin.com/in/felipe-de-lima-passarelli-6099362a0/">LinkedIn</a>
&nbsp;|&nbsp;
    <a href="https://www.instagram.com/felipe_de_lima_passarelli/">
    Instagram</a>
&nbsp;|&nbsp;</p>
</p>
<br/><br/>
<p>

---

⌨️ com 💜 por [Felipe de Lima Passarelli](https://github.com/Felipe-de-Lima-Passarelli)
