# Pandas (quick review)

## Importação 
Por convenção a biblioteca é importada e recebe o apelido 'alias' de 'pd'.

```
import pandas as pd
```

# Básico

## Ler arquivo csv
```
df = pd.read_csv('student_scores.csv')
```
Para arquivos com organização diferente de ';'
```
df = pd.read_csv('student_scores.csv', sep='-')
```

## Cabeçalhos

Alterar a linha de cabeçalho
```
df = pd.read_csv('student_scores.csv', header = 2)
```

Remover cabeçalho
```
df = pd.read_csv('student_scores.csv', header = None)
```

Alterar labels dos cabeçalhos
```
labels = ['id', 'name', 'attendance', 'test1', 'project1', ...]
df = pd.read_csv('student_scores.csv', names = labels)
```

Para substituir um cabeçalho
```
labels = ['id', 'name', 'attendance', 'test1', 'project1', ...]
df = pd.read_csv('student_scores.csv', header = 0, names = labels)
```

Coluna de índices
```
df = pd.read_csv('student_scores.csv', index_col = 'Name')
df = pd.read_csv('student_scores.csv', index_col = ['id', 'Name'])
```

## Exibir as primeiras linhas
```
df.head()   # Primeiras cinco linhas
df.head(5)  # Primeiras cinco linhas
df.head(20) # Primeiras 20 linhas
```

ou últimas linhas
```
df.tail()
df.tail(2)
df.tail(10)
```

## Gravar CSV
```
df.to_csv('student_scores_v2.csv')
```

# Sobre o dataframe
Formato, número de linhas e colunas
```
df.shape()
```

Tipos de dados das colunas
```
df.dtypes
```

Resumo conciso do dataframe, incluindo valores não nulos das colunas
```
df.info()
```

Número de valores únicos em cada coluna
```
df.nunique()
```

Retorna estatísticas descritivas úteis para cada coluna de dados
```
df.describe()
```

# Colunas
```
df.columns()
```

Listagem de colunas específicas
Para selecionar rótulos de linhas ou colunas ```loc```, para índices ```iloc```.
```
df.loc[:, 'id': 'fractal_dimension_mean'] # mesma notação de array [:] > [1:5]
df.iloc[:,:11]
```

## Para selecionar múltiplos intervalos no Pandas
Para selecionar múltiplos intervalos é necessário utilizar a biblioteca ```r_``` do pacote ```Numpy```. 
Explicação no [stackoverflow](https://stackoverflow.com/questions/41256648/select-multiple-ranges-of-columns-in-pandas-dataframe)

```
import numpy as np

df = df.iloc[: np.r_[0, 1, 1:22]]
df.head()
```

# Cleaning

## Preencher linhas com valor nulo
```
mean = df['view_duration'].mean()
df['view_duration'].fillna(mean, inplace = True)
```

## Identificar linhas duplicadas
```
df.duplicated()
```

## Somar linhas dublicadas
```
sum(df.duplicated())
```
## Remover linhas duplicadas
```
df.drop_duplicates(inplace = True)
```

## Conversão de tipos

Exemplo de conversão de string para ```datetime```
```
df['timestamp'] = pd.to_datetime(df['timestamp'])
```

Para reconhecer datas ao carregar, [documentação]
```
df = pd.read_csv('student_scores.csv', parse_dates = True)
# Lista de índices ou nomes
parse_dates = [1:2]
parse_dates = ['timestamp', 'birth']
```
