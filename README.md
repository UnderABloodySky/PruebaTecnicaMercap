# Prueba Técnica Mercap - 2021 
 
_Implementar en el lenguaje orientado a objetos que más te guste el siguiente ejercicio.
Realizar un sistema de facturación de llamadas telefónicas teniendo en cuenta los siguientes
requerimientos:
1) La facturación se realiza de manera mensual
2) La facturación está compuesta por:
a. Un abono mensual básico
b. Consumo por llamadas Locales
c. Consumo por llamadas Nacionales e Internacionales
3) Las llamadas locales tienen distintos valores según la franja horaria en la que se
realizan y el día. Para los días hábiles, de 8 a 20 hrs. el costo es de 0,20 centavos el
minuto, mientras en el resto de las horas es de 0,10 centavos el minuto. Los sábados
y domingos cuesta 0,10 centavos el minuto
4) Las llamadas Internacionales tienen un costo distinto según el país al que se llame
5) Las llamadas Nacionales tienen un costo distinto según la localidad a la que se
llame
Consideraciones adicionales:
1) No es necesario realizar una interfaz de usuario visual.
2) No es necesario realizar persistencia de los datos (o sea, conexión a base de datos,
archivos, etc.). Alcanza con simular los datos creándolos en memoria
3) Como salida alcanza ver por pantalla como sería una factura (sin preocuparse por
darle un formato especial)._

## Comenzando 🚀

_Estas instrucciones te permitirán obtener una copia del proyecto en funcionamiento en tu máquina local. Empecemos por clonar el [repositorio](https://github.com/UnderABloodySky/PruebaTecnicaMercap). y dirigirnos a la carpeta *Prueba tecnica mercap - Horacio Valenzuela*._ 
Mira **Deployment** para conocer como desplegar el proyecto.


### Pre-requisitos 📋

_Las *cosas* necesitas para instalar el software:_


- Pharo
- Windows x64bits.
- Alguna programa de compresion, por ejemplo _winRar_ o similar.

_Dentro de la carpeta **Prueba Tecnica Mercap - Horacio Valenzuela**, se pueden encontrar los archivos .change, .image y .sources._ 


### Instalación 🔧 y Despliegue 📦

_Mas allá de la instalación de los pre-requisitos, el proyecto no necesita de ninguna instalación previa. Para visualizarlo basta con abrir desde el Pharo Launcher el archivo **.image**, corriendo a este como administrador._

_El paquete a buscar, una vez dentro del proyecto, se llamada **PruebaTecnicaMercap**, corriendo a este como administrador._


### consideraciones 📦



_ * El abono fijo de una factura se determina al momento de instanciar a las mismas._
_ * Es indistinto si la llamada es Nacional o Internacional, dado que se delega en el lugar. Tal distincion, si bien util desde un punto de vista semantico/transcripción del ejercicio, en la práctica no apotababa lo que se considera nada de valor._

 

### Detalles 📦

**Todos los Dias** entiende los mensajes:
```
costo :: Retorna el costo del mismo
```

El **DiaHabil** entiende los mensajes:
```
costo :: Retorna el costo del mismo, considerando la franja horaria.
franja: unaFranja :: Modifica la franja horaria del dia
```

- El **DiaNoHabil** entiende el mensaje:
```
costo: aCosto :: Modifica el costo del dia
```

- La **Factura** entiende los mensajes:
```
abono :: Returna el abono fijo de la factura
abono: aAbono :: Modifica el abono de la factura
agregaLlamada: unaLlamada :: Agrega una llamada a las llamadas que componen a una factura.
costo :: Retorna el costo total de la factura (básico + llamadas)
costoLlamadas :: Retorna la sumatoria de los costos de todas las llamadas que componen a la factura
```

- Las **FranjasHorarias** (considerado para el DiaHabil) entienden el mensaje:
```
costo :: Retorna el costo del mismo.
```

- **Todas las llamadas** entienden los mensaje:
```
costo :: Retorna el costo del mismo (duracion x una consideracion propia de cada tipo de llamada).
costoPropio :: Retorna el costo, considerando el tipo de la llamada
duracion :: Retorna la duracion de la llamada
duracion:: aDuracion :: Modifica la duracion
```

- Por otro lado, las **LlamadasLocales** entienden los mensaje:
```
costoPropio :: Retorna el costo, se considera el lugar
dia: aDIa: Modifica el dia de la llamada
```


- Por otro lado, las **LlamadasNoLocales** entienden los mensaje:
```
costoPropio :: Retorna el costo, considerando el dia donde se realizo la misma. Lo mismo, si amerita, la franja horaria.
lugar: aLugar: Modifica el lugar de la llamada
```

## Construido con 🛠️

- [Smalltalk](https://www.smalltalk.org/) - Para el back-end (Utilizamos la version **3.6.8**).
- [Pharo](https://pharo.org/) - versión de imagen 9.0(stable).

## Autor ✒️
* [**Horacio Valenzuel**](https://github.com/UnderABloodySky)




---
⌨️ powered by NombrePendiente ❤️ 😊
