## Esquema para el ejercicio
![Imagen](esquema-ejercicio3.PNG)

### Crear red net-wp
```
docker network create net-wp
```

### Para que persista la información es necesario conocer en dónde mysql almacena la información.
En el esquema del ejercicio carpeta del contenedor (a) es /var/lib/mysql

Ruta carpeta host: .../ejercicio3/db

### ¿Qué contiene la carpeta db del host?
Nada, está vacía

### Crear un contenedor con la imagen mysql:8  en la red net-wp, configurar las variables de entorno: MYSQL_ROOT_PASSWORD, MYSQL_DATABASE, MYSQL_USER y MYSQL_PASSWORD
```
docker run -d \
  --name contenedor_mysql \
  --network net-wp \
  -v ~/ejercicio3/db:/var/lib/mysql \
  -e MYSQL_DATABASE=wordpress \
  -e MYSQL_USER=wp_user \
  -e MYSQL_PASSWORD=wp_pass \
  -e MYSQL_ROOT_PASSWORD=rootpass \
  mysql:8.0
```

```
docker run -d \
  --name contenedor_wordpress \
  --network net-wp \
  -p 9500:80 \
  -v ~/ejercicio3/www:/var/www/html \
  -e WORDPRESS_DB_HOST=contenedor_mysql:3306 \
  -e WORDPRESS_DB_USER=wp_user \
  -e WORDPRESS_DB_PASSWORD=wp_pass \
  -e WORDPRESS_DB_NAME=wordpress \
  wordpress:latest


```

### ¿Qué observa en la carpeta db que se encontraba inicialmente vacía?
# COMPLETAR CON LA RESPUESTA A LA PREGUNTA

### Para que persista la información es necesario conocer en dónde wordpress almacena la información.
# COMPLETAR LA SIGUIENTE ORACIÓN. REVISAR LA DOCUMENTACIÓN DE LA IMAGEN EN https://hub.docker.com/
En el esquema del ejercicio la carpeta del contenedor (b) es (COMPLETAR CON LA RUTA)

Ruta carpeta host: .../ejercicio3/www

### Crear un contenedor con la imagen wordpress en la red net-wp, configurar las variables de entorno WORDPRESS_DB_HOST, WORDPRESS_DB_USER, WORDPRESS_DB_PASSWORD y WORDPRESS_DB_NAME (los valores de estas variables corresponden a los del contenedor creado previamente)
# COMPLETAR CON EL COMANDO

### Personalizar la apariencia de wordpress y agregar una entrada

### Eliminar el contenedor y crearlo nuevamente, ¿qué ha sucedido?

# COMPLETAR CON LA RESPUESTA A LA PREGUNTA 

