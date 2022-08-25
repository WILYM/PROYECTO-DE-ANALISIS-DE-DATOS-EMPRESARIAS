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
- Introducción: Descripción del problema
- FUENTE DE LOS DATOS
- DESCRIPCIÓN DEL DATASET
- ANALITICAL TASKS
- GRÁFICAS DE ANÁLISIS
- INSIGHTS
## Descripcion del problema
- Los sismos ocurren cada día, normalmente se consideran desde 3.0 a la escala de Richter, no sabemos con qué frecuencia suceden los sismos cada año, si existe algún sismo que sucedió al mismo tiempo, y cómo afecta la profundidad y la magnitud a las construcciones y el alcance del movimiento en km.<br>
- No existe un análisis por escala o magnitud.<br>
- Existe poco estudio en el Perú sobre los sismos, aunque en los últimos años, están desarrollando un sistema “SISMATE” Sistema de Mensajería de Alerta Temprana de Emergencias por  INDECI y MTC.<br>

## Fuente de los datos
Los datos fueron extraidos de la base de datos de la [IGP](https://www.datosabiertos.gob.pe/dataset/catalogo-sismico-1960-2021-igp)
![Detalles](https://github.com/Romehe369/Analisis_Datos/blob/bd8cb5cca628d16804a3f3aa52d573e2c042be86/Date1.png)
## Objetivos
Realizamos un analisis de los datos de sismos del Perú, en la cual se muestra un mapa coropletico de los sucesos sismicos por region en el peru
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

Utilizando excel convertimos a un formate de fecha  : =CONCAT(EXTRAE(B2,1,4),"/",EXTRAE(B2,5,2),"/",EXTRAE(B2,7,2)) <br>
Utilizando excel convertimos a un formate de  hora  : =CONCAT(EXTRAE(C2,1,2),":",EXTRAE(C2,3,2),":",EXTRAE(C2,5,2))
![Detalles](https://github.com/Romehe369/Analisis_Datos/blob/0bf01ff03a74fe6e589f4a6de96e33259d5b2a76/Cap2.png)
- Relizamos conversion a nuestro horario de peru
Concatenamos los datos de fecha y hora, en caso de que la resta y tiempo haga referencia al dia anterior
=CONCAT(I2," ",H2)
Esta funcion afecta a la fecha y hora =NSHORA(RESIDUO(-5,24),0,0)+J2+ENTERO(-5/24) <br>
![Detalles](https://github.com/Romehe369/Analisis_Datos/blob/0bf01ff03a74fe6e589f4a6de96e33259d5b2a76/fecha%20y%20hora.png)
- utiliza Reverse Geocoding de google para obtener datos de la ubicación
![Detalles](https://github.com/Romehe369/Analisis_Datos/blob/53101962418fd9c8e520fc4f6fffbc062dda7091/Reverse.png)
- Para miles de datos utilizamos el google seets y su complemento apps script
y el codigo esta en <b>Geocodificacion.txt</b>:
![Detalles](https://github.com/Romehe369/Analisis_Datos/blob/53101962418fd9c8e520fc4f6fffbc062dda7091/direc1.png)
https://docs.google.com/spreadsheets/d/1yzd163-goiJOKRUHT3ZBEan8C6n4X2CabU50d16S-xA/edit?usp=sharing



## Resultado:

## Restricciones:
