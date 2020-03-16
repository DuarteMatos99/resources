**Author:** Duarte Matos
###### tags: `Python` `Pandas`

# Data Analytics

![](https://i.imgur.com/UnNHodF.png)

## The Scientific Python Ecosystem
### Core Packages
==NumPy== - The fundamental package for numerical computation.

==SciPyLibrary== - A collection of numerical algorithms and domain-specific toolboxes.

==Matplotlib== – Plotting and visualization package, 2D plotting and basic 3D plotting.

==SymPy== - For symbolic mathematics and computer algebra.

==Pandas== – Easy to use data structures for data science.

==IPython== – Interactive shell and web based notebook for rapid prototyping of ideas.

### Additional Packages
Doesn't make part of the core packages, but very important combined with core packages:
==Scikit-image== – Image processing library

==Scikit-learn== – Machine learning and AI library

==Jupyter== – Interactive web based notebook with code, visualizations, rich text, videos, and more

==h5py and PyTables== – Both access data stored in HDF5 format

==pytest== – Unit testing frameworks for python

# Jupyter

![](https://i.imgur.com/tFX4kOd.png)

## What is Jupyter?
The Jupyter Notebook is an open source web application that you can use to create and share documents that contain live code, equations, visualizations, and text. Jupyter Notebook is maintained by the people at Project Jupyter.

## Installation
If so, then you can use a handy tool that comes with Python called pip to install Jupyter Notebook on shell:
```
pip install jupyter
```

## Starting the Jupyter Notebook Server
Now that you have Jupyter installed, let’s learn how to use it. To get started, all you need to do is open up your terminal application and go to a folder of your choice. I recommend using something like your Documents folder to start out with and create a subfolder there called Notebooks or something else that is easy to remember.

Then just go to that location in your terminal and run the following command:
```
jupyter notebook
```

# NumPy

![](https://i.imgur.com/KnvBGNM.png)

## O que é o NumPy?
O NumPy é uma poderosa biblioteca Python que é usada principalmente para realizar cálculos em Arrays Multidimensionais. O NumPy fornece um grande conjunto de funções e operações de biblioteca que ajudam os programadores a executar facilmente cálculos numéricos. Esses tipos de cálculos numéricos são amplamente utilizados em tarefas como:

==Modelos de Machine Learning:== Ao escrever algoritmos de Machine Learning, supõe-se que se realize vários cálculos numéricos em Array. Por exemplo, multiplicação de Arrays, transposição, adição, etc. O NumPy fornece uma excelente biblioteca para cálculos fáceis (em termos de escrita de código) e rápidos (em termos de velocidade). Os Arrays NumPy são usados para armazenar os dados de treinamento, bem como os parâmetros dos modelos de Machine Learning.

==Processamento de Imagem e Computação Gráfica:== Imagens no computador são representadas como Arrays Multidimensionais de números. NumPy torna-se a escolha mais natural para o mesmo. O NumPy, na verdade, fornece algumas excelentes funções de biblioteca para rápida manipulação de imagens. Alguns exemplos são o espelhamento de uma imagem, a rotação de uma imagem por um determinado ângulo etc.

==Tarefas matemáticas:== NumPy é bastante útil para executar várias tarefas matemáticas como integração numérica, diferenciação, interpolação, extrapolação e muitas outras. O NumPy possui também funções incorporadas para álgebra linear e geração de números aleatórios. É uma biblioteca que pode ser usada em conjuto do SciPy e Mat-plotlib. Substituindo o MATLAB quando se trata de tarefas matemáticas.

## Instalacao de NumPy
```
pip install numpy
```

# Pandas

![](https://i.imgur.com/RnNdqCx.png)

## What's Pandas?
É uma biblioteca Python. Ela fornece ferramentas de análise de dados e estruturas de dados de alta performance e fáceis de usar.
Por ser a principal e mais completa biblioteca para estes objetivos, Pandas é fundamental para Análise de Dados.

## Getting started
To use pandas, you'll typically start with the following line of code.
```python=
import pandas as pd
```

## Creating data
==There are two core objects in pandas: the **DataFrame** and the **Series**.==

### DataFrame
A DataFrame is a table. It contains an array of individual entries, each of which has a certain value. Each entry corresponds to a row (or record) and a column.

In this example, the "0, No" entry has the value of 131. The "0, Yes" entry has a value of 50, and so on.

For example, consider the following simple DataFrame:
```python=
pd.DataFrame({'Yes': [50, 21], 'No': [131, 2]})
```
![](https://i.imgur.com/hKT4lNA.png)

We are using the pd.DataFrame() constructor to generate these DataFrame objects. The syntax for declaring a new one is a dictionary whose keys are the column names (Bob and Sue in this example), and whose values are a list of entries. This is the standard way of constructing a new DataFrame, and the one you are most likely to encounter.

DataFrame entries are not limited to integers. For instance, here's a DataFrame whose values are strings:
```python=
pd.DataFrame({'Bob': ['I liked it.', 'It was awful.'], 
            'Sue': ['Pretty good.', 'Bland.']})
```
![](https://i.imgur.com/dZDOTj3.png)

The dictionary-list constructor assigns values to the column labels, but just uses an ascending count from 0 (0, 1, 2, 3, ...) for the row labels. Sometimes this is OK, but oftentimes we will want to assign these labels ourselves.

The list of row labels used in a DataFrame is known as an Index. We can assign values to it by using an index parameter in our constructor:
```python=
pd.DataFrame({'Bob': ['I liked it.', 'It was awful.'], 
            'Sue': ['Pretty good.', 'Bland.']}, index=['A', 'B'])
```
![](https://i.imgur.com/XQ5KaNm.png)

### Series
A Series, by contrast, is a sequence of data values. If a DataFrame is a table, a Series is a list. And in fact you can create one with nothing more than a list:
```python=
pd.Series([1, 2, 3, 4, 5])
```
![](https://i.imgur.com/lZJMM3L.png)

```python=
pd.Series(['a', 'b', 'c', 'd'])
```
![](https://i.imgur.com/t7QHjKg.png)

A Series is, in essence, a single column of a DataFrame. So you can assign column values to the Series the same way as before, using an index parameter. However, a Series does not have a column name, it only has one overall name:
```python=
pd.Series([30, 35, 40], index=['2015 Sales', '2016 Sales', '2017 Sales'], 
            name='Product A')
```
![](https://i.imgur.com/nR25BiL.png)

The Series and the DataFrame are intimately related. It's helpful to think of a DataFrame as actually being just a bunch of Series "glued together". 

## Reading CSV file
Being able to create a DataFrame or Series by hand is handy. But, most of the time, we won't actually be creating our own data by hand. Instead, we'll be working with data that already exists.

Data can be stored in any of a number of different forms and formats. By far the most basic of these is the humble CSV file. When you open a CSV file you get something that looks like this:

![](https://i.imgur.com/dtmNuN4.png)

==So a CSV file is a table of values separated by commas. Hence the name: "Comma-Separated Values", or CSV.==

Let's now set aside our toy datasets and see what a real dataset looks like when we read it into a DataFrame. We'll use the pd.read_csv() function to read the data into a DataFrame. This goes thusly:
```python=
wine_reviews = pd.read_csv("../input/wine-reviews/winemag-data-130k-v2.csv")
```
We can use the ==shape== attribute to check how large the resulting DataFrame is:
```python=
wine_reviews.shape
```
![](https://i.imgur.com/4IKR84o.png) 129971 rows × 14 columns

So our new DataFrame has 130,000 records split across 14 different columns. That's almost 2 million entries!

We can examine the contents of the resultant DataFrame using the head() command, which grabs the first five rows:
```python=
wine_reviews.head()
```

![](https://i.imgur.com/75HfBcy.png)

The ==pd.read_csv()== function is well-endowed, with over 30 optional parameters you can specify. For example, you can see in this dataset that the CSV file has a built-in index, which pandas did not pick up on automatically. To make pandas use that column for the index (instead of creating a new one from scratch), we can specify an ==index_col==.
```python=
wine_reviews = pd.read_csv("../input/wine-reviews/winemag-data-130k-v2.csv",
index_col=0)
wine_reviews.head()
```
![](https://i.imgur.com/wDdkAwK.png)

## Save CSV file
A CSV file is a table of values separated by commas. To save files we utilize the keyword 'to_csv'.
```python=
animals = pd.DataFrame({'Cows': [12, 20], 'Goats': [22, 19]}, 
                        index=['Year 1', 'Year 2'])

# pandas.DataFrame.to_csv
animals.to_csv('cows_and_goats.csv')
```

## Naive Accessors
Native Python objects provide good ways of indexing data. Pandas carries all of these over, which helps make it easy to start with.

Consider this DataFrame:
```python=
reviews  # jupyter syntax
```

![](https://i.imgur.com/oAvqzHw.png)

In Python, we can access the property of an object by accessing it as an attribute. A book object, for example, might have a title property, which we can access by calling book.title. Columns in a pandas DataFrame work in much the same way.

Hence to access the country property of reviews we can use:
```python=
reviews.country
```

![](https://i.imgur.com/7ANpwoN.png)

If we have a Python dictionary, we can access its values using the indexing ([]) operator. We can do the same with columns in a DataFrame:
```python=
reviews['country']
```

![](https://i.imgur.com/pNnBuBI.png)

These are the two ways of selecting a specific Series out of a DataFrame. Neither of them is more or less syntactically valid than the other, but the indexing operator [] does have the advantage that it can handle column names with reserved characters in them (e.g. if we had a country providence column, reviews.country providence wouldn't work).

Doesn't a pandas Series look kind of like a fancy dictionary? It pretty much is, so it's no surprise that, to drill down to a single specific value, we need only use the indexing operator [] once more:
```python=
reviews['country'][0]
```

![](https://i.imgur.com/fhicdyz.png)


## Recursos
==Gratuitos:==
- Plataforma para aprender Pandas
https://www.kaggle.com/learn/pandas