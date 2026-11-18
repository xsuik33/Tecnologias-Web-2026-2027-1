# Bolsa de trabajo escuela–empresa

Proyecto de la materia Tecnologías para el Desarrollo de Aplicaciones Web, grupo 4CV3, periodo 2026-2027/1, impartida por el profesor Manuel Alejandro Soto Ramos en la Escuela Superior de Cómputo del Instituto Politécnico Nacional. El repositorio es trabajado por un equipo de cuatro integrantes.

## Descripción del sistema

El sistema es una bolsa de trabajo web que vincula a tres actores. El administrador de un centro educativo registra su institución dentro de un árbol jerárquico (por ejemplo, IPN → ESCOM), captura los planes de estudio con su año de vigencia y define los perfiles de egreso y las habilidades que cada plan forma. La empresa se registra, es validada y publica vacantes indicando las habilidades que requiere, el sueldo, el tipo de contrato, la modalidad y el horario. El egresado se registra con su boleta, es validado por su centro educativo, llena un CV base y se postula a las vacantes que coinciden con su formación. La aplicación se construye con HTML5, CSS3, JavaScript ES6 y Bootstrap en el cliente, PHP 8 con arquitectura MVC sobre Apache en el servidor y MySQL o MariaDB como gestor de base de datos.

## Metodología: modelo incremental

El desarrollo sigue el modelo incremental. En este modelo el sistema completo no se construye de una sola vez, sino que se divide en partes llamadas incrementos; cada incremento recorre las cuatro etapas de análisis, diseño, implementación y pruebas, y al terminar entrega una porción del sistema que ya funciona y puede demostrarse. El incremento siguiente se apoya en lo ya construido y solo comienza cuando el anterior fue probado, de modo que el producto crece de forma ordenada y los errores se detectan pronto, antes de que se acumulen.

Se eligió este modelo en lugar de una metodología ágil como Scrum porque el equipo es pequeño, los requisitos ya están definidos por el profesor y las etapas que se revisan en clase coinciden con las de cada incremento. Scrum exige roles fijos, reuniones diarias, sprints y retrospectivas que, en un proyecto escolar de pocas semanas, añadirían trabajo sin aportar valor. Con el modelo incremental cada entrega es demostrable en clase y la documentación de cada etapa se genera de forma natural.

## Etapas de cada incremento

Cada incremento se desarrolla en el mismo orden de cuatro etapas, y ninguna se da por terminada hasta que su resultado queda registrado en la carpeta correspondiente del repositorio.

En el **análisis** se determina qué debe hacer la parte del sistema que se va a construir. Para realizarlo, el equipo revisa los requisitos dados por el profesor, identifica qué actor participa, redacta los casos de uso y describe los procesos paso a paso. Esta etapa conlleva dejar por escrito qué se incluye y qué queda fuera del incremento, de manera que todos los integrantes trabajen sobre el mismo alcance.

En el **diseño** se decide cómo se construirá lo analizado. Se elaboran o amplían el diagrama entidad–relación, el diccionario de datos y el script de la base de datos, se dibujan los bocetos de las pantallas y se define la navegación entre ellas, así como los modelos, vistas y controladores de PHP que se necesitarán. Conlleva fijar los nombres de tablas, campos y archivos antes de programar, para evitar que dos integrantes resuelvan lo mismo de formas distintas.

En la **implementación** se programa lo diseñado. Cada integrante toma una parte del incremento, la desarrolla en su propia rama de Git y la integra al proyecto cuando funciona en su equipo local. Conlleva respetar la estructura MVC, mantener el estilo visual acordado y no modificar el trabajo de otro integrante sin avisar.

En las **pruebas** se comprueba que el incremento cumple lo establecido en el análisis. Se recorre cada caso de uso con datos de ejemplo, se verifica que cada rol solo acceda a sus funciones y se registran los errores encontrados junto con su corrección. Conlleva que el incremento solo se considere terminado cuando todas sus pruebas pasan; en ese momento se etiqueta la versión en el repositorio y comienza el análisis del incremento siguiente.

## Incrementos del proyecto

El sistema se divide en tres incrementos, cada uno centrado en uno de los actores.

| Incremento | Nombre | Contenido | Resultado demostrable |
|---|---|---|---|
| 1 | Base e instituciones | Base de datos completa, inicio de sesión por roles y panel del administrador del centro educativo para dar de alta la institución, el plan de estudios, los perfiles y las habilidades. | Un administrador inicia sesión y registra IPN → ESCOM con su plan y habilidades. |
| 2 | Empresa y vacantes | Registro y validación de la empresa, panel de la empresa, creación de vacantes y selección de las habilidades requeridas a partir de los planes registrados. | Una empresa validada publica una vacante con sus requisitos. |
| 3 | Egresado y postulación | Registro del egresado y validación con su centro educativo, llenado del CV base, búsqueda y detalle de vacantes, postulación y gestión de candidatos por parte de la empresa. | Un egresado se postula a una vacante y la empresa lo ve en su lista de candidatos. |

El primer incremento es la base de los demás, pues sin instituciones ni habilidades registradas no es posible definir los requisitos de una vacante; el segundo es requisito del tercero, ya que el egresado necesita vacantes publicadas para postularse. Por esta razón el orden de los incrementos no puede alterarse.

## Organización del repositorio

La documentación de cada etapa se guarda en las carpetas `1_Analisis`, `2_Diseno`, `3_Implementacion` y `4_Pruebas`, y el código fuente se ubica dentro de `3_Implementacion`. La rama `main` contiene siempre la última versión probada; cada integrante trabaja en una rama propia con el nombre del incremento y de su tarea (por ejemplo, `inc1-login`) y solicita la integración mediante un *pull request*, que otro integrante revisa antes de aceptarlo. Al cerrar cada incremento se crea una etiqueta con su número (`v1`, `v2` y `v3`).
