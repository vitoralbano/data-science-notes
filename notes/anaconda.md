## Data Science course

# Anaconda
Anaconda é um pacote de distribuição de software que vem com `conda`, que é python e mais de 150 pacotes científicos e suas dependências.

> ## Miniconda
> É uma distribuição menor que inclui somente Python e `conda`, os demais pacotes podem ser instalados manualmente.

`Conda` é exclusivamente utilizado em linha de comando (commandline) e com isso, também a administração de pacotes/bibliotecas instaladas.

> Para se acostumar com o uso linhas de comando, acesse [command prompt for Windows](https://www.lynda.com/-tutorials/Windows-command-line-basics/497312/513424-4.html) ou [Linux Command Line Basics](https://www.udacity.com/course/linux-command-line-basics--ud595).

## Gerenciamento de pacotes (Managing Packages)

`Conda` é similar ao `pip` do python, entretanto seus pacotes são focados em data science, ao passo que os do `pip` são mais de uso geral.

### Instalar pacotes
```
conda install package_name
conda install numpy pandas scipy
conda install numpy=1.10
```

### Desinstalar pacotes (remover)
```
conda remove package_name
```

### Atualizar pacotes
```
# Atualizar pacote específico
conda update package_name

# Atualizar todos os pacotes de um ambiente (environment)
conda update --all
```

### Procurar por pacotes (search)
```
conda search search_term
conda search beautifulsoup
```

---
## Ambientes (Environments)

Além de um **_managing packages_**, `conda` também é **_virtual environment manager_**, similar ao **_virtualenv_** do python. Ambientes permitem separar e isolar pacotes que são utilizados em diferentes projetos e assim evitando conflitos dos pacotes e versões de python.

## Instalando Anaconda

Disponível para Windows, Mac OS X e linux, as instruções para download e instalação estão em [https://www.continuum.io/downloads](https://www.continuum.io/downloads).

>    ## Windows
>    No windows um grupo de aplicações são instaladas juntos com **Anaconda**
>    * **Anaconda Navigator**, uma interface gráfica para gerenciar os ambientes e pacotes;
>    * **Anaconda prompt**, terminal (commandline) para gerenciar os ambientes e pacotes;
>    * **Spyder**, IDE voltada para o desenvolvimento científico;
>   

> ## Troubleshooting
> If you are seeing the following "conda command not found" and are using > ZShell, you have to do the following:
> 
> Add export PATH="/Users/username/anaconda/bin:$PATH" to your .zsh_config > file.


## Comandos de atualização
```
conda upgrade conda
conda upgrade --all
```

## Gerenciamento de ambientes
Com `Conda` é possível criar ambientes para isolar projetos. Para criar um ambiente, utilize:
```
conda create -n {env_name} [list of packages, ...]
```
>__-n__ é o parâmetro para nome do ambiente

É possível também, determinar a versão do Python do ambiente, por exemplo:
```
conda create -n py3 python=3
conda create -n py2 python=2
```

## Acessando ambientes
Com o ambiente criado, para acessa-lo entre com o comando:
```
OSX/Linux terminal: source activate my_env
Windows terminal: activate my_env
```

Com o ambiente ativado, ele será identificado no prompt do terminal como:
```
(my_env) ~ $
(my_env) C:\Users\User
```

Para sair do ambiente entre com o comando:
```
OSX/Linux terminal: source deactivate
Windows terminal: deactivate
```

Para listar os ambientes criados
```
conda env list
```

Remover ambientes:
```
conda env remove -n my_env
```

## Salvando e carregando ambientes
Um recurso muito prático é o compartilhamento de ambientes para que outros possam instalar os pacotes instalados no seu código. 
Para listar os pacotes instalados:
```
conda env export
```
Para salvar os pacotes em um arquivo [YAML](http://yaml.org/):
```
conda env export > environment.yaml
```
> ## Boas práticas
> * É considerada uma boa prática criar um ambiente para cada projeto
> * Ao compartilhar seu código no GitHub, é uma boa pratica criar um arquivo do ambiente e salva-lo no repositório. Isso irá fazilitar as pessoas de instalar as dependências. É interessante também incluir os requisitos do PIP, usando o `pip freeze`, para quem não usa conda ([saiba mais](https://pip.pypa.io/en/stable/reference/pip_freeze/))


> ## Mais dicas
> Para aprender mais sobre `conda` e como ele se encaixa no ecossistema do Python, leia o artigo do Jake Vanderplas: **[Conda myths and misconceptions](https://jakevdp.github.io/blog/2016/08/25/conda-myths-and-misconceptions/)** e também a [documentação](http://conda.pydata.org/docs/using/index.html) do `conda`


