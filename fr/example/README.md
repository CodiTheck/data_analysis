## Exemple d'analyse de donnée
![](https://img.shields.io/badge/lastest-2023--03--09-success)
![](https://img.shields.io/badge/status-en%20r%C3%A9daction%20-yellow)

Nous allons commencer ce chapitre en travaillant avec un exemple réel d'analyse et de traitement de données avec Python, nous n'allons pas encore entrer dans les détails, le chapitre suivante expliquera ce que fait chacun des outils, et quelle est la meilleure façon de les appliquer en les combinant. Je veux juste te montrer une référence rapide et de haut niveau des processus quotidiens, des analystes de données, des gestionnaires de données, des scientifiques de données utilisant Python. Le premier ensemble de données (dataset) que nous allons utiliser est un fichier CSV que tu peux trouver [ici](../../data/sales_data.csv).

Pour commencer, on importe les modules comme suit:

```python
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt

```

Si tu utilise un notebook, alors ajoute aussi la ligne de code suivante.

```python
%matplotlib inline
```

<details id="table-content" open>
    <summary>Table des Contenus</summary>
    <ul>
        <li><a href="#chargement-de-la-dataset">Chargement de la dataset</a> </li>
        <!-- <li><a href="#le-machine-learning">Le machine learning</a> </li> -->
        <!-- <li><a href="#différence-entre-ia-et-machine-learning">Différence entre IA et machine learning</a> </li> -->
    </ul>

</details>
<br/>

### Chargement de la dataset
La première chose que nous allons faire est donc de lire ce CSV dans Python, et vous pouvez voir à quel point c'est simple : une seule ligne de code, et le contenu du fichier est totalement chargé.

```python
# On charge tous le fichier dans une variable.
sales_dt = pd.read_csv('data/sales_data.csv', parse_dates=['Date'])

```

Ensuite, on peut afficher les 5 premières lignes avec la fonction `head()`.

```python
sales_dt.head()
```

Voici à quoi ressemble les données que nous avons chargées.

```
        Date  Day     Month  Year  Customer_Age       Age_Group  ... Order_Quantity Unit_Cost Unit_Price Profit  Cost Revenue
0 2013-11-26   26  November  2013            19     Youth (<25)  ...              8        45        120    590   360     950
1 2015-11-26   26  November  2015            19     Youth (<25)  ...              8        45        120    590   360     950
2 2014-03-23   23     March  2014            49  Adults (35-64)  ...             23        45        120   1366  1035    2401
3 2016-03-23   23     March  2016            49  Adults (35-64)  ...             20        45        120   1188   900    2088
4 2014-05-15   15       May  2014            47  Adults (35-64)  ...              4        45        120    238   180     418

[5 rows x 18 columns]
```

Ces données sont stockées sous la forme d'un type spécial qu'on appel `DataFrame`. Nous verrons cela plus en détail dans plus tard. Le contenu de notre variable `sales_dt` qui est un `DataFame` correspond à peu près à la représentation CSV, mais elle comporte quelques éléments supplémentaires. Par exemple, chaque colonne appartient à un type de données bien précis. Et on ne peut pas modifier cela.

Les dimensions de notre `DataFrame` de données nous indique le nombre de lignes et de colonnes que nous avons.

```python
print(sales_dt.shape)  # affiche (nombre de lignes, nombre de colonnes)

```

Cela affiche:

```
(113036, 18)
```

Tu peux donc imaginer qu'avec un tel nombre de lignes, et le fait qu'il ne sera pas aussi simple d'en avoir une représentation visuelle. Pour cela, on va d'abord utiliser la fonction `info()` pour afficher sur les colonnes avec lesquelles on veut travailler.

```python
print(sales_dt.info())
```

Ce qui produit le résultat suivant :

```
<class 'pandas.core.frame.DataFrame'>
RangeIndex: 113036 entries, 0 to 113035
Data columns (total 18 columns):
 #   Column            Non-Null Count   Dtype         
---  ------            --------------   -----         
 0   Date              113036 non-null  datetime64[ns]
 1   Day               113036 non-null  int64         
 2   Month             113036 non-null  object        
 3   Year              113036 non-null  int64         
 4   Customer_Age      113036 non-null  int64         
 5   Age_Group         113036 non-null  object        
 6   Customer_Gender   113036 non-null  object        
 7   Country           113036 non-null  object        
 8   State             113036 non-null  object        
 9   Product_Category  113036 non-null  object        
 10  Sub_Category      113036 non-null  object        
 11  Product           113036 non-null  object        
 12  Order_Quantity    113036 non-null  int64         
 13  Unit_Cost         113036 non-null  int64         
 14  Unit_Price        113036 non-null  int64         
 15  Profit            113036 non-null  int64         
 16  Cost              113036 non-null  int64         
 17  Revenue           113036 non-null  int64         
dtypes: datetime64[ns](1), int64(9), object(8)
memory usage: 15.5+ MB
None
```

Nous avons la date, qui est un champ de type `datetime`, ensuite, nous avons le jour, le mois, l'année, qui sont simplement complémentaires à la date, ensuite, l'âge du client, qui est un entier, ce qui est logique, n'est-ce pas ? Bref, nous avons une idée de la taille en mémoire de l'ensemble des données qu'on a chargée (15.5+ MB), nous avons des détails sur les colonnes. Avec toutes ces informations, nous avons une meilleure compréhension de la structure.

Et on peut aller plus loin, en utilisant la méthode `describe()`, on peut avoir une meilleure compréhension des propriétés statistiques de notre ensemble de données.

```python
statistic_desc = sales_dt.describe()
print(statistic_desc)
```

Ce qui donne :

```
                 Day           Year   Customer_Age  Order_Quantity  ...     Unit_Price         Profit           Cost        Revenue
count  113036.000000  113036.000000  113036.000000   113036.000000  ...  113036.000000  113036.000000  113036.000000  113036.000000
mean       15.665753    2014.401739      35.919212       11.901660  ...     452.938427     285.051665     469.318695     754.370360
std         8.781567       1.272510      11.021936        9.561857  ...     922.071219     453.887443     884.866118    1309.094674
min         1.000000    2011.000000      17.000000        1.000000  ...       2.000000     -30.000000       1.000000       2.000000
25%         8.000000    2013.000000      28.000000        2.000000  ...       5.000000      29.000000      28.000000      63.000000
50%        16.000000    2014.000000      35.000000       10.000000  ...      24.000000     101.000000     108.000000     223.000000
75%        23.000000    2016.000000      43.000000       20.000000  ...      70.000000     358.000000     432.000000     800.000000
max        31.000000    2016.000000      87.000000       32.000000  ...    3578.000000   15096.000000   42978.000000   58074.000000

[8 rows x 9 columns]
```



