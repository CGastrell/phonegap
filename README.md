Coderhouse

```todo el texto es ex profeso sin tildes con vocablos en ingles cuando es necesario```

# Phonegap
Curso de 39 horas a 3 horas por clase

  * 1 clase introductoria
  * 3 clases de introduccion a plugins
  * 1 clase de incorporacion de framework css y proyecto integrador
  * 3 clases de estudio de plugins
  * 1 clase de proyecto integrador
  * 3 clases de estudio de plugins y conformacion de app
  * 1 proyecto integrador final y revision de apps

## Introduccion

### Repaso de conceptos:: Programacion orientada a objetos (OOP)

La programacion orientada a objetos se refiere a la utilizacion de codigo "encapsulado" para desarrollar aplicaciones. Referimos como **objetos** a estos codigos "encapsulados", mejor conocidos como **Clases** en la mayoria de los lenguajes de programacion o **Funciones** en **Javascript**. Los objetos se usan como bloques de construccion para nuestras aplicaciones. Construir aplicaciones en base a objetos permite adoptar tecnicas eficientes como **Herencia** (objetos que pueden heredar caracteristicas de otros objetos), **Polimorfismo** (objetos que comparten un ancestro -interfaz- pero pueden diferir en la implementacion de sus metodos) y **Encapsulamiento** (cada objeto es responsable de tareas especificas). **Abstraccion** es una estrategia de encapsulamiento y, como es natural en la abstraccion, podra considerarse o no segun el nivel de abstraccion con el que se observe la funcionalidad del objeto.

```javascript
//Clase - Factory
function Vehiculo() {
  if(!(this instanceof Vehiculo)){
    return new Vehiculo();
  }
  this.puertas = 4;
  this.color = "negro";
}
//Metodos de clase
Vehiculo.prototype.getColor = function() {
  return this.color;
}

//Subclase
function Coupe(color) {
  Vehiculo.call(this);
  this.color = color || this.color;
  this.puertas = 2;
  return this;
}
//Herencia de clase
//heredar antes de cualquier aplicacion de polimorfismo!
Coupe.prototype = Object.create(Vehiculo.prototype);

//Polimorfismo - las funciones, heredadas o propias, pueden mutar
Coupe.prototype.getColor = function() {
  var color = this.color;
  if(color[color.length - 1] === "o") {
    color = color.substring(0, color.length - 1) + "a";
  }
  return "Coupe " + color;
}
```

### Repaso de conceptos:: API (Application Programming Interface)

Un conjunto de funciones y procedimientos que permiten la creacion de aplicaciones que acceden a caracteristicas o datos de un sistema operativo, aplicacion u otro servicio.

Una API se puede presentar como un recurso online, acceso a datos, librerias, servicios, etc...
```
//facebook API
/friends: Returns list of friends for logged in user
function getFriends(uid) {
  $query = "SELECT user_id, friends FROM friendsHABTM WHERE user_id = ".uid;
  return db.query($query);
}
///
response:
{
  user_id: {int},
  friends: {array}
}
```

#### ReSTful API

ReST: Representational State Transfer

Una API ReST es una (transferencia de la) representacion del estado del modelo de datos o la aplicacion.

Actualmente no existe un estandar de ReST dado que es solo una propuesta, pero cuenta con una adopcion masiva por parte de las APIs online:

  * amazon
  * mercadolibre
  * facebook
  * twitter
  * google
  * etc...

Las APIs exceden su definicion inicial de mera transferencia utilizando todos los verbos HTTP disponibles (GET, POST, PUT, DELETE, PATCH...)

### Events

  * Emitter API
  * Objetos Observables
  * Listeners
  * Job Queues
  * DOM


