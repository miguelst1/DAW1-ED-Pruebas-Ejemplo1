# DAW1-ED-Pruebas-Ejemplo1

[![Build Status](https://travis-ci.org/miguelst1/DAW1-ED-Pruebas-Ejemplo1.svg?branch=master)](https://travis-ci.org/miguelst1/DAW1-ED-Pruebas-Ejemplo1)

## Pruebas unitarias en **Java** con **JUnit4** 

### Código a testear (pruebas de unidad)

El código de la aplicación lo componen 3 clases:

- Main  (Clase principal)
- Aritmética
- Utilidades

La clase Main es la que hace uso de los métodos definidos en Aritmética y Utilidades.

Dentro de **Aritmética** tenemos 4 métodos estáticos:
- `suma`
- `resta`
- `multiplicacion`
- `division`
 
Dentro de **Utilidades** tenemos 1 métodos estático:
- `ordenar`  (para ordenar un array de 3 enteros)


### Requisitos

Es necesario el uso del sistema de construcción (build) **gradle**. Si trabajamos con NetBeans deberemos instalar el plugin para gradle. 

Asimismo, en el archivo [build.gradle](build.gradle) añadiremos la línea *apply plugin: "jacoco"* (Java Code Coverage), para poder realizar cobertura de código.


### Clases de prueba

Las clases de prueba son:

- MainTest
- AritméticaTest
- UtilidadesTest


### Servicios web utilizados

Se utilizan 2 servicios web:

- [Travis-CI.org](https://travis-ci.org/jamj2000/DAW1-ED-Pruebas-Ejemplo1): para ***integración continua*** (construcción y paso de tests)
- [Codecov.io](https://codecov.io/gh/jamj2000/DAW1-ED-Pruebas-Ejemplo1): para ***cobertura de código***
- [Sonarcloud.io](https://sonarcloud.io/organizations/jamj2000-github/projects): para ***análisis de calidad de código***

Es importante tener un archivo **`.travis.yml`** adecuado. Aquí tienes el utilizado en este proyecto:

- [.travis.yml](.travis.yml)

### Análisis de calidad de código

Para realizar un análisis de la calidad del código (bugs, vulnerabilidades, *code smells* y demás) nos hemos registrado con nuestra cuenta de GitHub en https://sonarcloud.io, hemos generado un *token* y hemos añadido este proyecto. 

Al principio del archivo [**`build.gradle`**](build.gradle) debemos escribir las líneas:

```
plugins {
  id "org.sonarqube" version "2.6"
}
```
Para realizar el análisis, ejecutamos la sentencia:

```
./gradlew sonarqube \
  -Dsonar.organization=jamj2000-github \
  -Dsonar.host.url=https://sonarcloud.io \
  -Dsonar.login=<token>
```
> NOTA: Debemos sustituir *\<token\>* por el generado previamente.

![Análisis de calidad del código](img/sonarqube-sonarcloud.png)







