## Data Science course

# Jupyter

## Instalação


Para instalar o kernel de **Ju**lia, **Py**thon, **R** e também notebook
```
conda install jupyter notebook
```

Para ter acesso ao ambiente `conda` é necessária a instalação do pacote **notebook conda** de nome **nb_conda**:

```
conda install nb_conda
```

## Iniciar o servidor (launch server)

Basta entrar com o comando abaixo no seu ambiente:
```
jupyter notebook
```


## Conversão
Since notebooks are JSON, it is simple to convert them to other formats. Jupyter comes with a utility called nbconvert for converting to HTML, Markdown, slideshows, etc.

For example, to convert a notebook to an HTML file, in your terminal use
```
jupyter nbconvert --to html notebook.ipyn
```