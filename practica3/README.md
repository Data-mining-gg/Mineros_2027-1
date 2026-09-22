# <center> Practica 3: Polars </center>

## <center>Integrantes <center>

<center>

| Nombre                         | Número de cuenta |
|:------------------------------:|:----------------:|
| Vega Navas Saúl                | 322088267        |
| Cimmino Yáñez Nicholas Joseph  | 322490712        |
| Benítez Pérez Kristian Leonel  | 322011346        |
| Herrera Cuamatla Jennifer Jade | 322255481        |

</center>

## Objetivo

En esta práctica se pondrá aprueba y a evaluación los siguientes puntos:

+ Aprender a estructurar correctamente un proyecto de mineria de datos
+ Seleccionar un framework de análisis de datos de manera correcta según el problema y los datos a analizar
+ Aplicar un preprocesamiento de los datos (normalización, eliminación de duplicados, conversión de tipos de datos e imputación) dados. 
+ Calcular e interpretar medidas de localización y variabilidad para un análisis exploratorio.

##  Fuente de los datos

La fuente de datos  oficial se obtuve del gobierno mexicano sobre violencia contra las mujeres, que esta disponible en este [enlace](https://www.inegi.org.mx/programas/endireh/2021/), en la sección de Microdatos, donde se descargó la base de datos en formato _csv_  y se juntó todos los archivos en un solo archivo csv, así como tambien se descargo el descriptor de archivos en formato _pdf_.

##  Instalación del entorno

Para poder instalar el entorno para ejecutar el programa es necesario ejecutar en la terminal
lo siguiente:

#### Windows:
```
python -m venv venv
pip install -r requirements.txt 
```

#### Mac o Linux:
```
python3 -m venv venv
pip install -r requirements.txt
```

## Ejecutar el  pipeline
Desde `proyecto-endireh-violencia`, para ejecutar el codigo de Preprocesamiento:

####  - Windows:
``` powershell
python -m src.cleaning.preprocessing 
```
####  - Mac o Linux:
``` bash
python3 -m src.cleaning.preprocessing
```

Para ver que hacen los Jupyter notebook, basta con abrirlos con VSCode o con cualquier otro lector de Jupyter notebook.

En el reporte se encuentra todos los Jupyter notebooks con sus respectivos resultados de cada codigo ejecutado.


## Cuestionario

**1.- Al tratarse de un tema social sensible como la violencia contra las mujeres, ¿qué consideraciones éticas debe tener el equipo de análisis al interpretar y presentar los resultados
del EDA?**

Al ser analizados los datos sobre violencia contra las mujeres en el EDA, como equipo debemos mantener las siguientes consideraciones éticas:
* Evitar la revictimización y estigmatizar: Al interpretar los datos considerando los factores que forman al problema, no habrá que buscar culpables en las víctimas ni reforzar ningún tipo de estereotipo de género o prejuicios así cmo evitar generalizar.
Por lo que es importante tomar un lenguaje adecuado y no generalizador ante este análisis.
* Presentar datos o gráficas aisladas sin el debido contexto metodológico; ya sea omitir los factores de expansión o ignorar el diseño muestral, puede conducir a conclusiones erróneas o alarmantes que distorsionen la realidad del fenómeno social. 
* También hay que reconocer que la violencia no afecta a todas las mujeres de la misma manera. Este análisis debe contemplar cómo interactúan variables socioeconómicas, escolaridad, edad o entidad federativa para poder entender la complejidad del problema sin caer en determinismos.
* El procesamiento de datos debe realizarse de la mejor manera para garantizar que los resultados reflejen con fidelidad la realidad capturada por la encuesta, asegurando transparencia en las limitaciones del dataset.

**2.- Se calculó la media simple de edad primer union y también la media ponderada por factor expansión. ¿Por qué pueden diferir ambos valores, y cuál de las dos es más representativa de la población nacional de mujeres de 15 años y más?**

Los valores pueden diferir porque en la encuesta la **media simple** asume que todas las mujeres encuestadas tiene el valor de 1 es decir, 1 persona = 1 voto.
Y la **media ponderada** multiplica cada respuesta por su ***factor_expansion*** porque en otras encuestas como las que realiza INEGI dado que es a grandes masas; una sola mujer puede representar a 500 0 1000 mujeres de su ciudad o estado o municipio. 

La más representativa es la media ponderada ya que refleja la realidad del país ajustándose a cada región y ajusta la muestra para poder representar a todas las mujeres de 15 años en México.


**3.- Si el coeficiente de variación de edad-primer-union resulta considerablemente más alto en el grupo que reportó violencia de pareja que en el que no, ¿qué hipótesis plantearíamos para explicarlo, y qué otra variable del dataset ayudaría a confirmar o descartar?**

Si la situación es verdadera, entonces podemos plantear una hipótesis sobre la distribución, declarando que la concentración de situaciones de violencia de pareja no se da hacia un rango de edades concreto, sino que puede ser una mezcla entre las edades consideradas como tempranas, por causas derivadas de la alta vulnerabilidad de esos sectores; y las consideradas como comunes, por causas diferentes a las primeras mencionadas.

Esto se puede respaldar o refutar con factores como estrato_socioeconomico y nivel_escolaridad, pudiendo confirmar si las uniones a edades tempranas se asocian con situaciones de bajos recursos y baja escolaridad que derivan en los escenarios de vulnerabilidad planteados en la hipótesis, o si, por el contrario, dichos valores tienen baja heterogeneidad a lo largo del intervalo de edades.


**4.- Compara la media simple de edad_primer_union contra la media ponderada por factor_expansion.¿Por qué pueden diferir? ¿Cuál de las dos debería reportarse si el objetivo es describir a la población nacional y no solo a la muestra encuestada?**

Las cifras difieren porque la media simple asume erróneamente que cada persona en la base de datos tiene exactamente la misma probabilidad de haber sido encuestada, lo que hace que todos los registros tengan la misma validez; no obstante, el factor de expansión añade valores de importancia para abarcar los efectos del encapsulamiento de sectores poblacionales completos en representaciones que, sin dicho factor, se consideran para una única persona.

Es por esto que, al buscar describir no solo al conjunto de personas entrevistadas, sino a la población nacional, se debe reportar la media ponderada, pues las cantidades de personas que ésta engloba permite generalizar los resultados para reflejar estadísticamente al país completo.


**5.- Si el coeficiente de variación de edad-primer-union resulta considerablemente más alto en el grupo que reportó violencia de pareja que en el que no, ¿qué hipótesis plantearíamos para explicarlo, y qué otra variable del dataset ayudaría a confirmar o descartar?**

Si la situación es verdadera, entonces podemos plantear una hipótesis sobre la distribución, declarando que la concentración de situaciones de violencia de pareja no se da hacia un rango de edades concreto, sino que puede ser una mezcla entre las edades consideradas como tempranas, por causas derivadas de la alta vulnerabilidad de esos sectores; y las consideradas como comunes, por causas diferentes a las primeras mencionadas.

Esto se puede respaldar o refutar con factores como estrato_socioeconomico y nivel_escolaridad, pudiendo confirmar si las uniones a edades tempranas se asocian con situaciones de bajos recursos y baja escolaridad que derivan en los escenarios de vulnerabilidad planteados en la hipótesis, o si, por el contrario, dichos valores tienen baja heterogeneidad a lo largo del intervalo de edades.
