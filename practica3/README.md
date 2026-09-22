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

## Cuestionario

**1.- Al tratarse de un tema social sensible como la violencia contra las mujeres, ¿qué consideraciones éticas debe tener el equipo de análisis al interpretar y presentar los resultados
del EDA?**

Al ser analizados los datos sobre violencia contra las mujeres en el EDA, como equipo debemos mantener las siguientes consideraciones éticas:
* Evitar la revictimización y estigmatizar: Al interpretar los datos considerando los factores que forman al problema, no habrá que buscar culpables en las víctimas ni reforzar ningún tipo de estereotipo de género o prejuicios así como evitar generalizar, por lo que es importante tomar un lenguaje adecuado y no generalizador ante este análisis.
* Presentar datos o gráficas aisladas sin el debido contexto metodológico, ya sea omitir los factores de expansión o ignorar el diseño muestral, puede conducir a conclusiones erróneas o alarmantes que distorsionen la realidad del fenómeno social. 
* Reconocer que la violencia no afecta a todas las mujeres de la misma manera. Este análisis debe contemplar cómo interactúan variables socioeconómicas, escolaridad, edad o entidad federativa para poder entender la complejidad del problema sin caer en determinismos.
* El procesamiento de datos debe realizarse de la mejor manera para garantizar que los resultados reflejen con fidelidad la realidad capturada por la encuesta, asegurando transparencia en las limitaciones del dataset.

**2.- Se calculó la media simple de edad primer union y también la media ponderada por
factor expansión. ¿Por qué pueden diferir ambos valores, y cuál de las dos es más
representativa de la población nacional de mujeres de 15 años y más?**

Los valores pueden diferir porque en la encuesta la **media simple** asume que todas las mujeres encuestadas tiene el valor de 1 es decir, 1 persona = 1 voto.
Y la **media ponderada** multiplica cada respuesta por su ***factor_expansion*** porque en otras encuestas como las que realiza INEGI dado que es a grandes masas; una sola mujer puede representar a 500 0 1000 mujeres de su ciudad o estado o municipio. 

La más representativa es la media ponderada ya que refleja la realidad del país ajustándose a cada región y ajusta la muestra para poder representar a todas las mujeres de 15 años en México.


**3.- Si el coeficiente de variación de edad-primer-union resulta considerablemente más alto
en el grupo que reportó violencia de pareja que en el que no, ¿qué hipótesis plantearía
para explicarlo, y qué otra variable del dataset ayudaría a confirmar o descartar?**

El Coeficiente de Variación al ser más alto significa que las edades del grupo con violencia se encuentran más _“dispersos”_ y no agrupados alrededor de un promedio. Esto sucede porque la violencia afecta a mujeres en circunstancias distintas como las que se juntaron o casaron siendo muy jóvenes (hay más vulnerabilidad y dependencia en todo sentido), y también están las mujeres que se juntaron o casaron a una edad más adulta, entonces estos casos extremistas hace que los datos varíen bastante en comparación con el grupo sin violencia que es más uniforme.

por ejemplo para poder comprobarlo tenemos estas variables;
* ***nivel_escolaridad***: Ayuda a saber si las mujeres que se unieron más jóvenes tienen menor grado de estudios y si ahí se encuentra un nicho de violencia.
* ***diferencia_edad_pareja***: Ayudaría a verificar si ciertos tipos de violencia o diferencias de edad agravan la variabilidad en la edad de la primera unión.
* ***estado_civil*** o ***edad_actual***: Ayudaría a revisar si la dispersión cambia según la edad que se tiene ahorita o la etapa de la vida en la que se encuentran.

