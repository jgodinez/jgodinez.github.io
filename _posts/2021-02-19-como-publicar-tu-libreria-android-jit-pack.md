---
layout: post
title: ¿CÓMO PUBLICAR TU LIBRERÍA DE ANDROID CON JITPACK?
author: juan
---

Hace años, cuando comencé a utilizar librerías en Android me surgió la interrogante sobre como es que había multiples desarroladores que generaban componentes y los compartían como librería, así que decidí investigar al respecto y encontré una solución bastante sencilla y muy común, la cual seguramente ya habrás podido ver implementada en algún proyecto. 


Pues bien, si a ti te interesa saber como poder realizar tus propias librerías y publicarlas, has llegado al lugar indicado.

<!--more-->

En esta ocasión vamos a utilizar [JitPack](https://jitpack.io/ "JitPack"), un gran gestor de paquetes para proyectos JVM y Android, el cual es completamente gratuito para librerías de código abierto. OJO, cabe mencionar que existen diferentes planes de uso para repositorios privados de Git si así lo requieres, pero para este post nos enfocaremos al plan gratuito.

Acorde a lo mencionado en su documentación oficial, es tan simple que sólo requieres cargar tu proyecto en una cuenta de GitHub y JitPack se encargará que tu librería esté disponible para su uso a nivel mundial. Veamos que tan cierto es.

Para este post tomaremos como ejemplo el proyecto [dotsindicator](https://github.com/jgodinez/dotsindicator "dotsindicator")

Comenzaremos creando y configurando nuestro repositorio en nuestra cuenta de github

![add repository]({{site.baseurl}}/images/git-new-repository.png)

Una vez creado el repositorio, crearemos nuestro proyecto en android studio agregando un nuevo módulo de tipo `Android Library` en donde agregaremos el código de nuestra librería. Ya que terminamos y probamos el proyecto, procederemos a agregarlo al repositorio previamente creado, para esto tomaremos nuestra terminal y ejecutaremos los siguientes comandos:

```git
git init
git remote add origin https://github.com/user/repository.git
git add .
git commit -m "first commit"
git push -u origin master
```

Despues de aseguraremos que el código está en nuestro repositorio de github, crearemos el primer release, el cual nos servirá como versión para nuestro artifact. Si nuestro poryecto no tiene ninguna release, se puede utilizar un commit o SNAPSHOT como versión.

![release]({{site.baseurl}}/images/git-rc.png)

Ahora accederemos a [jitpack](https://jitpack.io/ "jitpack"), agregaremos la url de nuestro repositorio y daremos clic en el boton `Look up`, ahi nos mostraran las diferentes versiones de nuestro código, tomaremos la que querramos exponer como librería y daremos clic en el botón `Get it`, esperamos la validación de esta y estaremos listos para poder comenzar a utilizarla. 

![release]({{site.baseurl}}/images/jitpack-rc.png)

Nota: En caso de fallas en la validación se deberá corregir acorde al archivo de log y volver a solicitar la validación.

El siguiente paso será configurar las dependencias del proyecto para comenzar a utilizar nuestra librería

## Dependency

**Step 1.** Add the JitPack repository to your root build.gradle file
```gradle
allprojects {
    repositories {
        ...
        maven { url 'https://jitpack.io' }
    }
}
```
   
**Step 2.** Add the dependency
```gradle
dependencies {
    implementation 'com.github.jgodinez:dotsindicator:1.0.0'
}
```

Un escenario que puedes llegar a experimentar si usas versiones SNAPSHOT es que no veas cambios al publicarlos, para corregir esto sólo recesitas agregar la siguiente configuración como se menciona en su [documentación oficial](https://jitpack.io/docs/ "docs") 

```gradle
configurations.all {
    resolutionStrategy.cacheChangingModulesFor 0, 'seconds'
}
``` 
