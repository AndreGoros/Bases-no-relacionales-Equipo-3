# Tráfico Aéreo en Tiempo Real con OpenSky
![flights_map](images/flights_map.png)
## Bases de Datos No Relacionales | Equipo 3

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
