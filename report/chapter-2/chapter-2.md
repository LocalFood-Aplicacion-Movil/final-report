# Capítulo II: Requirements Elicitation & Analysis

## 2.1. Competidores.

### 2.1.1. Análisis competitivo.

#### 2.1.2. Estrategias y tácticas frente a competidores

### 2.2. Entrevistas

#### 2.2.1. Diseño de entrevistas

#### 2.2.2. Registro de entrevistas

#### 2.2.3. Análisis de entrevistas

### 2.3. Needfinding

#### 2.3.1. User Persona

#### 2.3.2. User Task Matrix

#### 2.3.3. User Journey Mapping

#### 2.3.4. Empathy Mapping

#### 2.3.5. Ubiquitous Language

## 2.4. Requirements specification
### 2.4.1. User Stories
| EPICA                   | ID EPICA |
| ----------------------- | -------- |
|  Configuraciones orientadas a personas: <br>  Como nuevo usuario, quiero que las característica importantes sea intuitivas relacionado respecto a amigos/contactos, para poder realizar seguimiento o no al respecto <br> |  EP01  |
|  Registro y configuraciones internas: <br>  Como usuario de la plataforma, quiero que las herramientras de la plataforma sean moldeable respecto al calculo, para obtener un resultado independientemente del cambio de decisiones <br> |  EP02  |
|  Personalización de preferencias de grupo: <br> Como usuario, quiero configurar mis preferencias de grupo  para que el cálculo se adapte a mis necesidades y las de mis amigos.  <br> |  EP03  |
|  Flexibilidad en cálculos dinámicos: <br> Como usuario, quiero que el sistema permita recalcular automáticamente cuando cambien las condiciones del grupo, para mantener resultados actualizados. <br> |  EP04  |
| Seguimiento y visualización de resultados: <br> Como usuario, quiero visualizar de manera clara los cálculos y resultados, para tomar decisiones rápidas junto con mi grupo. <br> |  EP04  |

| Epic/ Story ID | Titulo | Description | Criterios de Aceptacion | Relacion con (Epic ID) |
|----------------|--------|-------------|-------------------------|---------------------|
| US01 | Ver notificaciones de amigos/contactos | Como nuevo usuario, quiero estar informado de las solicitudes de amistad como calculos que realizen mi lista de contactos para estar informado de actividades que puedan incluirme |Escenario 1: Visualizar Calculos hechos que me incluya <br> Dado que estoy en cualquier parte de la pagina, cuando veo las notificaciones, entonces puedo ver el usuario de la persona respecto a calculos o me envie solicitud de amistad. | EP01 |
| US02 | Cambiar de restaurante durante el calculo | Como usuario, quiero cambiar de resturante durante el calculo para poder adecuar el destinos a cambios de planes |Escenario 1: Realizar el cambio en cualquier momento antes de calcular: <br> Dado que soy un usuario que coordina con si grupo cuando veo que deciden cambiar de restaurante luego de haber coordinado uno, cuando acceda a Restaurante o Calculo, entonces se cambia el restaurante para el calculo. <br> Escenario 2: Realizar el cambio luego de hacer unos calculos: <br> Dado que soy un usuario que ya empezo a calcular con un restaurante para mi grupo, cuando cambiamos de opinion, entonces puedo presionar el boton de cambiar restaurante en cambio y sin forma de nuevo el grupo. | EP02 |
| US03 | Ignorar los cálculos de otra gente | Como usuario, quiero poder ignorar o rechazar los calculos, para no afectar el calculo de mis amigos como no tener muchas notificaciones |Escenario 1: Rechazar calculo que incluyan a cierto usuario: <br> Dado que soy un usuario que recibe notificaciones de calculos que me incluyan cuando acceda a la pagina con la notificacion, entonces presiono en el boton de denegar para que no me aparezca dicho calculo. <br>  | EP01 |
| US04 | Implementar amigos a un lista ya creada | Como usuario, quiero poder implementar mas amigos en una lista ya creada, para no tener que volverla a crear |Escenario 1: Un compañero nuevo se une a la reunion: <br> apartado de calculo con la lista ya creada, entonces presiono la opcion de incluir miembro a la lista ya creada y empiezo el calculo. <br>  | EP02 |
| US05 | Tener una opción de filtros | Como nuevo usuario, quiero tener una opcion de filtros respecto a restaurante de calidad para que el calculo sea conforma a todo o solo los mejores |Escenario 1: Buscar restaurante de calidad: <br> Dado que quiero comer con mis amigos en lugares bien valorados, cuando busco un restaurante en la apliacion y selecciono uno, entonces puedo presionar la opción de solo los mejor valorados de 5 estrellas para el calculo. <br>  | EP02 |
| US06 | Agregar amigos rápidamente | Como nuevo usuario, quiero poder agregar a mis lista a personas mas fácilmente para no demorarme o confundirme en el buscador |Escenario 1: Buscar restaurante de calidad: <br> Dado que quiero agregar a un nuevo amigo a la aplicaciones de forma rapida, cuando entre al aplicacion y entre a contacto, entonces presionare el boton de nuevo contacto y subire su codigo QR para agregarlo. <br>  | EP01 |
| US07 | Definir distancia máxima de búsqueda | Como usuario, quiero establecer una distancia máxima en kilómetros para que el sistema solo recomiende restaurantes dentro de ese rango                   | Escenario 1: Configurar distancia máxima <br> Dado que estoy configurando mis preferencias, cuando establezco una distancia máxima en kilómetros, entonces el sistema solo recomendará restaurantes dentro de ese rango. | EP03  |
| US08 | Seleccionar tipo de comida preferida | Como usuario, quiero elegir un tipo de comida (ejemplo: italiana, peruana, vegetariana) para que el cálculo priorice restaurantes de ese tipo              | Escenario 1: Configurar tipo de comida <br> Dado que estoy en la sección de configuraciones, cuando elijo un tipo de comida, entonces el cálculo prioriza restaurantes de ese tipo.                          | EP03  |
| US09 | Guardar configuraciones de grupo     | Como usuario, quiero guardar mis preferencias de grupo para que se apliquen automáticamente en futuros cálculos                                           | Escenario 1: Aplicar configuraciones guardadas <br> Dado que ya configuré mis preferencias, cuando inicio un nuevo cálculo con mis amigos, entonces el sistema aplica automáticamente esas configuraciones. | EP03  |
| US10 | Recalcular al añadir un nuevo amigo  | Como usuario, quiero que el sistema recalculé automáticamente cuando un nuevo amigo se una al grupo                                                       | Escenario 1: Añadir nuevo amigo <br> Dado que estoy realizando un cálculo con mi grupo, cuando un nuevo amigo se une, entonces el sistema recalcula automáticamente la ubicación óptima del restaurante.    | EP04  |
| US11 | Recalcular al eliminar un amigo      | Como usuario, quiero que el sistema ajuste el cálculo cuando un amigo salga del grupo                                                                     | Escenario 1: Eliminar amigo del cálculo <br> Dado que estoy en medio de un cálculo, cuando un amigo decide salir del grupo, entonces el sistema ajusta el cálculo y muestra nuevas recomendaciones.          | EP04  |
| US12 | Ajustar cálculo por cambios de transporte | Como usuario, quiero que el sistema considere cambios en el medio de transporte de mis amigos para recalcular tiempos de llegada                        | Escenario 1: Cambiar medio de transporte <br> Dado que algunos amigos cambian su medio de transporte, cuando actualizan su configuración, entonces el sistema recalcula considerando el nuevo tiempo de llegada. | EP04  |
| US13 | Ver mapa con ubicaciones de amigos   | Como usuario, quiero visualizar un mapa con la ubicación de mis amigos y el restaurante sugerido                                                           | Escenario 1: Visualizar mapa <br> Dado que estoy en la pantalla de resultados, cuando se muestra el mapa, entonces puedo ver la ubicación de cada amigo y el restaurante sugerido en relación a ellos.       | EP05  |
| US14 | Comparar restaurantes sugeridos      | Como usuario, quiero comparar las opciones de restaurantes sugeridos en base a distancia, tipo de comida y tiempo estimado                                | Escenario 1: Comparar opciones <br> Dado que el sistema me da varias opciones, cuando accedo a la lista de restaurantes, entonces puedo comparar distancia, tipo de comida y tiempo estimado de llegada.     | EP05  |
| US15 | Recibir resumen del cálculo          | Como usuario, quiero recibir un resumen del cálculo con el restaurante elegido, distancia promedio y tiempo estimado                                      | Escenario 1: Ver resumen del cálculo <br> Dado que el cálculo ya terminó, cuando veo el resumen, entonces puedo leer un informe con el restaurante elegido, la distancia promedio y el tiempo estimado.      | EP05  |

### 2.4.2. Impact Mapping

![mapping](/report/chapter-2/assets/Impact%20map.png)

### 2.4.3. Product Backlog

| # Orden | User ID | Título                                   | Descripción                                                                                                                                                          | Story Points(1 / 2 / 3 / 5 / 8) |
| ------- | ------- | ---------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ |
| 1       | US01    | Ver notificaciones de amigos/contactos   | Como nuevo usuario, quiero estar informado de las solicitudes de amistad como cálculos que realicen mi lista de contactos para estar informado de actividades que puedan incluirme | 5            |
| 2       | US03    | Ignorar los cálculos de otra gente       | Como usuario, quiero poder ignorar o rechazar los cálculos, para no afectar el cálculo de mis amigos ni tener muchas notificaciones                                  | 3            |
| 3       | US04    | Implementar amigos a una lista ya creada | Como usuario, quiero poder implementar más amigos en una lista ya creada, para no tener que volverla a crear                                                         | 5            |
| 4       | US05    | Tener una opción de filtros              | Como nuevo usuario, quiero tener una opción de filtros respecto a restaurantes de calidad para que el cálculo sea conforme a todo o solo los mejores                 | 3            |
| 5       | US06    | Agregar amigos rápidamente               | Como nuevo usuario, quiero poder agregar a mi lista a personas más fácilmente para no demorarme o confundirme en el buscador                                         | 2            |
| 6       | US07    | Definir distancia máxima de búsqueda     | Como usuario, quiero establecer una distancia máxima en kilómetros para que el sistema solo recomiende restaurantes dentro de ese rango                              | 8            |
| 7       | US08    | Seleccionar tipo de comida preferida     | Como usuario, quiero elegir un tipo de comida (ejemplo: italiana, peruana, vegetariana) para que el cálculo priorice restaurantes de ese tipo                        | 5            |
| 8       | US09    | Guardar configuraciones de grupo         | Como usuario, quiero guardar mis preferencias de grupo para que se apliquen automáticamente en futuros cálculos                                                     | 8            |
| 9       | US10    | Recalcular al añadir un nuevo amigo      | Como usuario, quiero que el sistema recalculé automáticamente cuando un nuevo amigo se una al grupo                                                                 | 5            |
| 10      | US11    | Recalcular al eliminar un amigo          | Como usuario, quiero que el sistema ajuste el cálculo cuando un amigo salga del grupo                                                                                | 5            |
| 11      | US12    | Ajustar cálculo por cambios de transporte | Como usuario, quiero que el sistema considere cambios en el medio de transporte de mis amigos para recalcular tiempos de llegada                                    | 8            |
| 12      | US13    | Ver mapa con ubicaciones de amigos       | Como usuario, quiero visualizar un mapa con la ubicación de mis amigos y el restaurante sugerido                                                                     | 2            |
| 13      | US14    | Comparar restaurantes sugeridos          | Como usuario, quiero comparar las opciones de restaurantes sugeridos en base a distancia, tipo de comida y tiempo estimado                                          | 5            |
| 14      | US15    | Recibir resumen del cálculo              | Como usuario, quiero recibir un resumen del cálculo con el restaurante elegido, distancia promedio y tiempo estimado                                                | 3            |
| 15       | US02    |   Registro y configuraciones internas              |   Como usuario, quiero cambiar de resturante durante el calculo para poder adecuar el destinos a cambios de planes  | 8            |


## 2.5. Strategic-Level Domain-Driven Design
### 2.5.1. EventStorming
#### 2.5.1.1. Candidate Context Discovery
#### 2.5.1.2. Domain Message Flows Modeling
#### 2.5.1.3. Bounded Context Canvases

### 2.5.2. Context Mapping

### 2.5.3. Software Architecture
#### 2.5.3.1. Software Architecture Context Level Diagrams
#### 2.5.3.2. Software Architecture Container Level Diagrams
#### 2.5.3.3. Software Architecture Deployment Diagrams

## 2.6. Tactical-Level Domain-Driven Design

### 2.6.x. Bounded Context: <Bounded Context Name>
#### 2.6.x.1. Domain Layer
#### 2.6.x.2. Interface Layer
#### 2.6.x.3. Application Layer
#### 2.6.x.4. Infrastructure Layer
#### 2.6.x.5. Bounded Context Software Architecture Component Level Diagrams
#### 2.6.x.6. Bounded Context Software Architecture Code Level Diagrams
##### 2.6.x.6.1. Bounded Context Domain Layer Class Diagrams
##### 2.6.x.6.2. Bounded Context Database Design Diagram
