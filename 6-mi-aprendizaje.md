## Conocimientos Antes de la Práctica

Antes de realizar esta práctica, tenía una comprensión general sobre cómo Docker aísla aplicaciones dentro de contenedores, pero no comprendía en profundidad cómo manejar la persistencia de datos.Tampoco entendía la diferencia entre _bind mounts_ y _volúmenes_, ni cómo estos influyen en el rendimiento.

## Durante la Práctica

Aprendí que Docker ofrece varias formas de gestionar el almacenamiento de datos:

* Volúmenes: creados y administrados por Docker, ideales para datos persistentes.
* Bind mounts: enlazan directamente carpetas del host con el contenedor, permitiendo trabajar con archivos locales.
* Volúmenes nombrados: permiten identificar fácilmente un volumen y reutilizarlo en distintos contenedores.
* Volúmenes anónimos: útiles para almacenamiento temporal, pero difíciles de administrar posteriormente.

Con los ejercicios pude aplicar estos conceptos de forma práctica.

## Problemas Encontrados y Solución

Durante los ejercicios, uno de los principales inconvenientes fue el _403 Forbidden_ al usar bind mounts vacíos. Aprendí que Docker reemplaza el contenido del contenedor con el del host, por lo que es necesario que la carpeta del host contenga los archivos adecuados antes de iniciar el contenedor.
