# MilkTankerTruckAAS
Asset Administration Shell of a Milk Tanker Truck

This AAS was generated using AASX Package Explorer (https://github.com/admin-shell-io/aasx-package-explorer)

A continuación, se describe cómo se estructuraron los datos del AAS del tanque según los aspectos comunes que poseen. El Asset Administration Shell propuesto para el Tanque de transporte de leche se organizó con los siguientes submodelos:
Submodelo de propiedades generales
- Submodelo de datos de GPS
- Submodelo de datos de caudalímetro
- Submodelo de termómetros (externo y en cada cisterna)
- Submodelo de phímetros (en cada cisterna)
- Submodelos de cisternas 1, 2, 3, 4, y 5.

<img width="100%" alt="image" src="https://github.com/lucianaroldan/MilkTankerTruckAAS/assets/1086796/84773c90-738c-4664-893f-d6255482b734">

A continuación, se describen cada uno de los submodelos que componen al Asset Administration Shell del tanque de transporte. Por cada submodelo, se presenta su representación en la herramienta AAS Package Explorer, junto con una tabla donde se indica su nombre (IdShort), tipo de elemento, de qué otro elemento en del AAS depende, tipo de valor (o tipo de dato), categoría (Parameter, Variable o Constant), descripción, y una breve justificación de su utilidad para el negocio. 
 El submodelo “Propiedades generales” define una serie de parámetros que caracterizan al vehículo de transporte en que está instalado el tanque (patente), marca y modelo del tanque, su conductor, y la ruta a seguir (remito).

<img width="70%" alt="image" src="https://github.com/lucianaroldan/MilkTankerTruckAAS/assets/1086796/bf344b71-abb7-4296-9978-1c91ae6dc657">

Submodelo de propiedades generales

Tabla. Descripción de elementos del Submodelo Propiedades generales
![image](https://github.com/lucianaroldan/MilkTankerTruckAAS/assets/1086796/64220053-8717-4306-b1fe-2a8c6de34377)


El submodelo “GPS” define los parámetros que caracterizan al dispositivo GPS (marca, modelo, fecha de mantenimiento) y la variable que indica la localización del camión en tiempo real. Por otro lado, el submodelo Caudalímetro define los parámetros que caracterizan al dispositivo empleado para medir los litros de leche cargados.

<img width="70%" alt="image" src="https://github.com/lucianaroldan/MilkTankerTruckAAS/assets/1086796/6cc2c656-a70e-42d8-b9b2-daf64d730151">

Descripción de elementos de los Submodelos GPS y Caudalímetro
![image](https://github.com/lucianaroldan/MilkTankerTruckAAS/assets/1086796/e5705c6f-572c-4bcb-b96c-68297f2f0ca2)

El submodelo “Termómetros” considera a los termómetros o sensores de temperatura instalados en cada cisterna, y al termómetro externo del camión. Por cada termómetro se define una submodel collection que contiene los parámetros que caracterizan al termómetro (marca, modelo, fecha de mantenimiento). En particular, para el termómetro externo se define una variable para representar la temperatura externa medida en tiempo real.  El submodelo se detalla a continuación, donde se presenta un ejemplo de submodel collection para un termómetro de cisterna.

<img width="70%" alt="image" src="https://github.com/lucianaroldan/MilkTankerTruckAAS/assets/1086796/73b5d16b-f71e-4b96-b84b-a6f62390dafc">

Submodelo Termómetros

Tabla. Descripción de elementos del Submodelo Termómetros
![image](https://github.com/lucianaroldan/MilkTankerTruckAAS/assets/1086796/dc3f95c9-8faf-424a-8af7-b47f1df3969a)
(*) se repite la submodel collection para cada cisterna

El submodelo “PHímetros” considera a los dispositivos para medición del PH en cada cisterna. Por cada PHímetro se define una submodel collection que contiene los parámetros que caracterizan al dispositivo (marca, modelo, fecha de mantenimiento). Las mediciones realizadas por estos dispositivos, se representan en los submodelos de cisternas que se indican más adelante. El submodelo se detalla a continuación:
<img width="70%" alt="image" src="https://github.com/lucianaroldan/MilkTankerTruckAAS/assets/1086796/314e0d5d-f5a0-4329-a915-07835144c42e">

Submodelo PHimetros y Submodel collections de los datos del phímetro en cada cisterna

Tabla. Descripción de elementos del Submodelo PHimetros
![image](https://github.com/lucianaroldan/MilkTankerTruckAAS/assets/1086796/afb0e4aa-2081-4101-9498-9c68c168c2f0)

Luego, se define un submodelo “Cisterna” por cada cisterna que posee el tanque (en total 5).  La representación propuesta posibilita agrupar los datos relativos a los momentos de carga (Submodel collection Carga), transporte, y descarga (Submodel collection Descarga) de cada cisterna. Dado que en cada cisterna puede cargarse leche de más de un tambo (máximo 3), se definen submodel collections “Tambo” para agrupar los datos relativos a la carga realizada por cada tambo. 
Entre las variables, se destacan aquellas que representan las mediciones realizadas por los dispositivos en el camión como Volumen_cargado, Temperatura_carga, y Temperatura_descarga (datos generado por el caudalímetro), temp_cisterna (dato generado por el termómetro en cada cisterna), y PH_cisterna (dato generado por el PHímetro en cada cisterna). Un ejemplo de submodelo (Cisterna01)  se detallan a continuación.

<img width="70%" alt="image" src="https://github.com/lucianaroldan/MilkTankerTruckAAS/assets/1086796/27d1a9a4-63ba-4afd-8641-f82e989492ce">

Submodelo de la Cisterna01

Tabla. Descripción de elementos del Submodelo Cisterna 

![image](https://github.com/lucianaroldan/MilkTankerTruckAAS/assets/1086796/8e734f22-1f65-48ca-9056-b5dc46f35dbb)

(*) se repite el submodelo para cada cisterna
(**) se repite la submodel collection para cada tambo
















