# PROYECTO-DE-ANALISIS-DE-DATOS-EMPRESARIAS
- **Universidad:** Universidad Nacional de San Antonio Abad del Cusco
- **Facultad:** De ingenieria electrica, electronica, informatica y mecanica
- **Escuela Profesional:** Ingenieria Informatica y de Sistemas
#### Docente:
Germain Garcia Zanabria
#### Colaboradores:
-CHOQUECONZA QUISPE NORGAN SANDRO<br> 
-HUAHUATICO SORIA RONALD<br> 
-MUNOZ MUNOZ WILY RODRIGO<br> 
## Tabla de Contenido
- DESCRIPCIÓN DEL PROBLEMA
- FUENTE DE LOS DATOS
- OBJETIVOS
- DESCRIPCIÓN DEL DATASET
- TRANSFORMACIÓN DE DATOS
- ANALITICAL TASKS
- GRÁFICAS DE ANÁLISIS

## Descripcion del problema
- Los sismos ocurren cada día, normalmente se consideran desde 3.0 a la escala de Richter, no sabemos con qué frecuencia suceden los sismos cada año, si existe algún sismo que sucedió al mismo tiempo, y cómo afecta la profundidad y la magnitud a las construcciones y el alcance del movimiento en km.<br>
- No existe un análisis por escala o magnitud.<br>
- Existe poco estudio en el Perú sobre los sismos, aunque en los últimos años, están desarrollando un sistema “SISMATE” Sistema de Mensajería de Alerta Temprana de Emergencias por  INDECI y MTC.<br>

## Fuente de los datos
Los datos fueron extraídos de la base de datos de la [IGP](https://www.datosabiertos.gob.pe/dataset/catalogo-sismico-1960-2021-igp)
![Detalles](https://github.com/Romehe369/Analisis_Datos/blob/bd8cb5cca628d16804a3f3aa52d573e2c042be86/Date1.png)
## Objetivos
Realizamos un análisis de los datos de sismos del Perú, en la cual se muestra un mapa coroplético de los sucesos sísmicos por región en el Perú.
## Descripción del dataset
Las dimensiones del data set son:
- 23712 registros de sismos
- 7 campos
![Detalles](https://github.com/Romehe369/Analisis_Datos/blob/0bf01ff03a74fe6e589f4a6de96e33259d5b2a76/Cap1.png)
- ID: Indica el numero de sismo
- FECHA_UTC: Corresponde al tiempo Coordinated Universal Time. 
- HORA_UTC: Corresponde al tiempo, Perú(UTC -5)
- LATITUD : Es la distancia en grados, minutos y segundos que hay con respecto al paralelo principal, que es el ecuador.
- LONGITUD: Es la distancia en grados, minutos y segundos que hay con respecto al meridiano principal, que es el meridiano de Greenwich.
- PROFUNDIDAD : Implica a cuantos km de la capa terrestre se detectó el movimiento.
- MAGNITUD : Indica la escala en la que sucedió.

### Transformación de datos

Utilizando excel convertimos a un formato de fecha  : =CONCAT(EXTRAE(B2,1,4),"/",EXTRAE(B2,5,2),"/",EXTRAE(B2,7,2)) <br>
Utilizando excel convertimos a un formato de  hora  : =CONCAT(EXTRAE(C2,1,2),":",EXTRAE(C2,3,2),":",EXTRAE(C2,5,2))
![Detalles](https://github.com/Romehe369/Analisis_Datos/blob/0bf01ff03a74fe6e589f4a6de96e33259d5b2a76/Cap2.png)
- Relizamos conversión a nuestro horario de Perú <br>
Concatenamos los datos de fecha y hora, en caso de que la resta (UTC-5) y tiempo haga referencia al dia anterior, entonces disminuimos en hora y fecha
=CONCAT(I2," ",H2) <br>
Esta función afecta a la fecha y hora =NSHORA(RESIDUO(-5,24),0,0)+J2+ENTERO(-5/24)  <br><br>
![Detalles](https://github.com/Romehe369/Analisis_Datos/blob/0bf01ff03a74fe6e589f4a6de96e33259d5b2a76/fecha%20y%20hora.png)
- utiliza Reverse Geocoding de google para obtener datos de la ubicación
![Detalles](https://github.com/Romehe369/Analisis_Datos/blob/53101962418fd9c8e520fc4f6fffbc062dda7091/Reverse.png) <br>
- Para miles de datos utilizamos el google seets y su complemento apps script
y el codigo esta en <b>Geocodificacion.txt</b>:
![Detalles](https://github.com/Romehe369/Analisis_Datos/blob/53101962418fd9c8e520fc4f6fffbc062dda7091/direc1.png) <br>
https://docs.google.com/spreadsheets/d/1yzd163-goiJOKRUHT3ZBEan8C6n4X2CabU50d16S-xA/edit?usp=sharing
## Analitical tasks
TASK 1:
Determinar regiones altamente sísmicas.

TASK 2:
¿Porqué sucede? 

TASK 3:
¿Que se esta realizando para concientizar a la población?

## Gráficas de análisis
TASK 1: Hallamos la cantidad de sismos ocurridos por cada región y generamos un mapa coroplético.<br>
![Detalles](https://github.com/Romehe369/Analisis_Datos/blob/2546605d6198c81175eca2835a64cb7179655cde/Mapa.png) <br>

TASK 2:
Principalmente existen mayor cantidad de sismos en el Perú por el proceso de subducción originado por la convergencia de las placas de Nazca ubicada en el océano  y Sudamericana la continental. En el Perú se distinguen dos modos de subducción, subhorizontal en las regiones norte y centro, y subducción normal en la región sur. En la actualidad, estudios de GPS han permitido conocer que el proceso de subducción se realiza con velocidades del orden de 7 a 9 cm/año.
TASK 3:
Existen redes acelerográficas, es un arreglo de varios acelerógrafos colocados en una región de interés para conocer características del subsuelo donde se instalan. Los acelerógrafos están integrados por sensores de aceleración y un registrador que mide las aceleraciones del suelo provocadas principalmente por los sismos.<br>
RED ACELEROGRÁFICA SENCICO <br>
![Detalles](https://github.com/Romehe369/Analisis_Datos/blob/c245e09304e9fe3216050cf3b7585b13c2e30e92/Acelerografias.png)
<br>RED ACELEROGRÁFICA EN CUSCO <br>
![Detalles](https://github.com/Romehe369/Analisis_Datos/blob/c245e09304e9fe3216050cf3b7585b13c2e30e92/acele.png)
- Sismos por magnitud maximo por años <br>
![Detalles](https://github.com/Romehe369/Analisis_Datos/blob/c7df2594322928ed0a9ac0e3cae885e6c201fe5b/graficosismos.png)
- Cantidad de sismos por años<br>
![Detalles](https://github.com/Romehe369/Analisis_Datos/blob/c7df2594322928ed0a9ac0e3cae885e6c201fe5b/sismo%20anios.png)

- Cantidad de sismos por horas <br>
![Detalles](https://github.com/Romehe369/Analisis_Datos/blob/ec44aade1e654410b01227588deb85c60f2bea56/horas.png)

- ¿Puede la posición de la luna o de los planetas afectar la sismicidad? ¿Hay más terremotos en la mañana/en la tarde/en un momento determinado del mes?

Varios estudios recientes han encontrado una correlación entre las mareas terrestres (causadas por la posición de la luna con respecto a la tierra) y algunos tipos de terremotos. Un estudio, por ejemplo, concluye que durante las épocas de mareas terrestres y oceánicas más altas, como durante las épocas de luna llena o luna nueva, los terremotos son más probables en fallas de cabalgamiento poco profundas cerca de los bordes de los continentes y en zonas de subducción (submarinas). Las mareas terrestres y especialmente las mareas oceánicas elevan y reducen la presión de confinamiento en fallas de inmersión poco profundas cerca de los bordes continentales y en zonas de subducción.
Cuando se reduce la presión de confinamiento, las fallas se liberan y es más probable que se deslicen. La mayor probabilidad es un factor de ~3 durante las mareas altas. <br>
Fuente: https://www.usgs.gov/faqs/can-position-moon-or-planets-affect-seismicity-are-there-more-earthquakes-morningin-eveningat


