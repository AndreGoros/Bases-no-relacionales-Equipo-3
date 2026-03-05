# Tráfico Aéreo en Tiempo Real con OpenSky
![flights_map](images/flights_map.png)
## Bases de Datos No Relacionales | Equipo 3

## Enlaces a la API y documentación del stream

Documentación y recursos oficiales:

- **Documentación oficial de la REST API:**  
  https://opensky-network.org/apidoc/rest.html

- **Sitio oficial de OpenSky Network:**  
  https://opensky-network.org

- **Repositorio de documentación y ejemplos de uso:**  
  https://github.com/openskynetwork

- **Biblioteca Python para consumir la API:**  
  https://github.com/openskynetwork/opensky-api


---

## Descripción del stream de datos

El stream de datos utilizado en este proyecto proviene de la **OpenSky Network**, una red global de sensores que recolecta información transmitida por aeronaves mediante tecnología **ADS-B (Automatic Dependent Surveillance–Broadcast)** y **Mode-S**. Estas señales son emitidas periódicamente por los transpondedores de los aviones y contienen información sobre su estado de vuelo.

La plataforma OpenSky recopila estas señales desde miles de receptores distribuidos en todo el mundo y las pone a disposición a través de una API pública que permite consultar el estado actual de las aeronaves.

Cada evento dentro del stream corresponde a un **state vector** de una aeronave en un momento determinado. Un state vector describe el estado del avión e incluye múltiples atributos, entre ellos:

- Identificador único del avión (`icao24`)
- Callsign del vuelo
- País de origen del registro de la aeronave
- Posición geográfica (latitud y longitud)
- Altitud
- Velocidad
- Dirección o rumbo del vuelo
- Tasa de ascenso o descenso
- Timestamps de posición y último contacto

Estos datos permiten reconstruir la dinámica del tráfico aéreo global en tiempo casi real. El propósito de este stream es facilitar el análisis del comportamiento del tráfico aéreo, el estudio de patrones de vuelo, la detección de anomalías en trayectorias y el análisis espacial y temporal de la densidad de aeronaves en diferentes regiones.

En este proyecto, cada state vector se considera un **evento del stream**, lo que permite modelar el flujo de datos como una serie de observaciones temporales de aeronaves que pueden ser almacenadas y analizadas utilizando una arquitectura de bases de datos NoSQL.


## Información general



## Origen y Autoría




### Diccionario de Datos
El stream de OpenSky Network transmite el estado de aeronaves detectadas por la red de sensores ADS-B. Cada registro representa la información más reciente de una aeronave en un momento determinado.
| Atributo | Definición técnica | Tipo de dato |
|-----------|-----------|-----------|
|Hex ID  | Identificador único ICAO de la aeronave    | String    |
|Callsign| Identificador del vuelo asignado por la aerolínea    | String    |
|Route   | Ruta estimada del vuelo entre aeropuerto origen y destino   |  String  |
|Registration  |   Matrícula oficial de la aeronave  | String   |
|Type  | Modelo o tipo de aeronave   |  String  |
|Squawk   | Código transponder asignado por control de tráfico aéreo  |  Integer  |
|Alt (ft)	| Altitud actual de la aeronave	| Numérico (pies) |
|Spd (kt)	| Velocidad horizontal del avión	| Numérico (knots) |
|V. Rate (ft/min) |	Tasa de ascenso o descenso del avión	| Numérico (pies/minuto) |
|Dist (nm)	| Distancia estimada respecto al receptor	| Numérico (millas náuticas) |
|Track |	Dirección de movimiento del avión	| Numérico (grados) |
|Messages	| Número de mensajes ADS-B recibidos	| Integer |
|Seen	| Tiempo desde el último mensaje recibido |	Numérico (segundos) |
|RSSI	| Intensidad de señal recibida	Numérico (dB) |
|Latitude |	Latitud de la aeronave	| Numérico (grados) |
|Longitude	| Longitud de la aeronave	| Numérico (grados) |
|Source	| Tipo de fuente de datos (ej. ADS-B)	| String |
|Mil.	| Indicador de aeronave militar	| Boolean |
|Wind D.	| Dirección del viento estimada |	Numérico (grados) |
|Wind (kt)	| Velocidad del viento	| Numérico (knots)|

### Variables Cuantitativas
Las variables cuantitativas corresponden a atributos numéricos que describen el estado físico y dinámico de las aeronaves.
Entre ellas se encuentran:
- Alt (ft) – altitud de vuelo
- Spd (kt) – velocidad del avión
- V. Rate (ft/min) – velocidad vertical
- Dist (nm) – distancia respecto al receptor
- Track – dirección de desplazamiento
- Latitude – coordenada geográfica de latitud
- Longitude – coordenada geográfica de longitud
- Messages – número de mensajes recibidos
- Seen – tiempo desde el último contacto
- RSSI – intensidad de señal
- Wind D. – dirección del viento
- Wind (kt) – velocidad del viento
- Estas variables permiten analizar patrones de tráfico aéreo, velocidad, altitud, trayectoria y condiciones ambientales del vuelo.

## Variables Cualitativas



## Texto No Estructurado



## Series Temporales


## Consideraciones Éticas
