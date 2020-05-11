---
layout: post
title: PRINCIPIOS EN EL DESARROLLO DE SOFTWARE
author: juan
---

En los últimos años he visto diversos lenguajes de programación aparecer y otros tantos actualizarse, la industria cambia de forma constante, por lo cual durante un tiempo me enfoqué en aprender lo nuevo de "X" lenguaje y dejé de lado "buenas prácticas" del desarrollo de software, pero sentía que ese proceso no estaba bien, que la calidad de mi código no era buena, así que comencé a estudiar sobre **principios en el desarrollo de software** y aplicarlos en mis desarrollos con la finalidad de comprenderlos mejor y poder compartir mi aprendizaje.

<!--more-->

Hoy puedo decir con base en mi experiencia que escribir código de calidad puede ser complejo, pero no por ello debemos dejar de lado las buenas prácticas, así que de forma personal y resumida les comparto un poco de lo aprendido.

DRY (Don't repeat yourself)

No escribir código duplicado. 

#### Problema

En trabajos colaborativos es común encontrar código duplicado, propenso a errores y difícil de mantener. 

#### Solución

Extraer y encapsular código, de esta forma el cambio se centraliza en un solo punto

* * *


KISS (Keep It Simple Stupid)

Mantenlo simple

#### Problema

Se crea código general con la expectativa de solventar múltiples problemas a la vez, lo que ocasiona complejidad innecesaria cuando el código crece 

#### Solución

Evita complejidad innecesaria, crea soluciones particulares que resuelvan problemas específicos

* * *


YAGNI (You ain't gonna need it)

No implementar código si no estás seguro de necesitarlo

#### Problema

Cuando se crea código, tiendes a incluir funcionalidades que no es seguro que se vayan a necesitar, pero crees que pueden servir en algún momento, lo cual satura el código de funcionalidad innecesaria

#### Solución

Evita implementar código que no estés completamente seguro de que se vaya a utilizar, no te anticipes a situaciones futuras, ya que en la mayorías de los casos se vuelve *código zombie*

* * *


SoC (Separation of Concerns)

Identifica y separa los asuntos en diferentes secciones

#### Problema

Se escribe el código como un sólo bloque que contiene múltiples componentes en lugar de dividir en pequeños módulos 

#### Solución

Dividir el código en bloques pequeños donde cada bloque sea capaz de ejecutar una sóla acción y diferente de las demás

* * *


The Boy Scout rule (Leave the code cleaner than how you found it)

Deja el código mejor de lo que lo encontraste. 

* Los Boy Scouts tienen una regla con respecto al campamento, que deben dejar el campamento más limpio de lo que lo encontraron.

#### Problema

Cuando el código crece en forma desmedida y se vuelve difícil de mantener a tal punto en el cual es mejor reescribir todo

#### Solución

Refactorizar con la finalidad de simplificar el código existente y tener mejora continua

* * *


LoD (Law of Demeter)

Un objeto debe conocer lo menos posible la estructura o propiedades de otros componentes

* No hables con extraños

#### Problema

Cuando se invocan métodos o propiedades de un objeto devueltos por otro objeto. Un objeto de clase A puede solicitar un método de un objeto instanciado de clase B, pero no de forma directa 

#### Solución

Enfocarse en mantener un bajo acoplamiento entre clases 

HP (Hollywood Principle)  Don't call us, we'll call you".

Una clase debe obtener las referencias necesarias para su ejecución de forma externa, no debe crear sus propios recursos

* No nos llame, nosotros le llamaremos

#### Problema

Existe demasiada relación y dependencia entre clases/módulos

#### Solución

Mantener bajo acoplamiento respecto de las demás clases y alta cohesión para sí misma, su enfoque debe ser particular y de único propósito.

* * *


SOLID

### Single Responsibility Principle

Una clase debe tener una sóla responsabilidad, es decir, sólo debe hacer una cosa de forma simple y concreta; en caso contrario debemos dividirla

### Open/Close Principle

Una clase debe ser abierta para la extensión y cerrada para su modificación, es decir el comportamiento de una clase puede ser extendido agregando código sin tener que modificar el código ya existe, salvo para corrección de errores

### Liskov Substitution Principle

Los subtipos deben poder ser reemplazados por sus tipos base sin alterar el funcionamiento. Es decir, el comportamiento no debe verse afectado al sustituir una implementación concreta por otra. El código debe hacer referencia a abstracciones y no a implementaciones a fin de mantener la integridad del mismo

### Interface Segregation Principle

Las interfaces deben tener de igual forma una sóla responsabilidad, es preferible dividir y tener múltiples interfaces específicas en lugar de crear una sola interfaz de propósito general, ya que esto obligaría a las clases a implementar métodos que no necesitan. 

### Dependency Inversion Principle

Debemos depender de abstracciones y no de implementaciones. Las dependencia directas entre clases deben ser sustituidas por abstracciones.

#### Problema

Cuando el desarrollo se conforma por diferentes módulos y múltiples colaboradores es susceptible de tener redundancias de código, clases cuya finalidad es realizar más de una tarea a la vez, código zombie debido a una mala abstracción de clases base, creación de recursos dentro de los propios componentes lo cual dificulta la realización de pruebas, entre otros.

#### Solución

Aprendizaje de los principios y comprensión de los mismos, tenerlos en cuenta durante el desarrollo e implementación de soluciones a fin de tener un buen diseño y que el mantenimiento sea sencillo.



#### Por último, desde un punto de vista personal 


> Los principios o "buenas prácticas" en el desarrollo de software no son complejos de “aprender”, lo complicado es poder implementarlos de forma correcta, esto requiere de experiencia, mucha práctica y sobre todo tener las ganas de mejorar y cambiar paradigmas.


[... s*i yo fuera objeto, sería objetivo; como soy sujeto, soy subjetivo...* | *José Bergamín*]
