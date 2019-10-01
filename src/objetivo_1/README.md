### Consigna:
En un corpus de texto general **en castellano**, encontrar grupos de palabras que puedan ser usados como clases de equivalencia.
### Librerias utilizadas

### Clustering is comming
Para la obtención de clusters en este trabajo se realizaron los siguientes pasos:
##### Preprocesamiento
El corpus utilizado fue obtenido de SBWCE <sup>1<sup>, al mismo se le eliminaron las palabras denominadas **stopwords**, la palabra **DIGITO** y los documentos que tenian menos de 8 palabras.
Se utilizo la libreria [**spacy**](https://spacy.io/), el procedimiento definido en el  *pipeline* consiste en *tagger*, y *parser*.
Analisis morfologico, es decir se identifica la categoría gramatical de una palabra. 
##### Seleccion de caracteristicas
Luego de preprocesar el corpus, se extrajo de cada *token* caracteristicas que posee el misma, esto se represento por medio de un diccionario, el cual contiene lo siguiente:
```python
{   'word':     value,
    'pos':      value,
    'lemma':    value,
    'is_lower': value,
    'dt':       value,
    'pre_word': value,
    'pos_word': value
}
```
donde *word* es el string del token, *POS* part-of-speech tags del token, *lemma* forma canonica del token, *is_lower* si el token esta en minuscula, *dt* representa las tripla de dependencia, *pre_word* el token anterior, *pos_word* token posterior(tamaño de ventana uno).
Una situacion que surge con esta forma de representar las caracterisitcas de las palabras es que al generar el diccionario de features de cada token, la ocurrencia de una palabra ya procesada tendra su propias caracteristicas, como consecuncia puede causar que en distintos cluster aparezcan las mismas palabras.
##### Vectorizado
Para el vectorizado de las caracteristicas se utilizo Dictvectorizer() de sklearn.
##### Reduccion de dimensionalidad
Para la reduccion de la dimensionalidad LSA.

##### Grafico de elbown

![elbow](elbow.png)

##### Clustering

### Conclusiones

### Referencias
1. [Cristian Cardellino: Spanish Billion Words Corpus and Embeddings (March 2016)]( https://crscardellino.github.io/SBWCE/)