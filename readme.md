# Crear un enrutamiento y Balanceo de carga con NGINX

Para crear este ejercicio lo dividimos en 2 paginas web llamada

- index.html
- index2.html

Crearemos nuesta propia red tipo bridge y le asignaremos a la red nuestras paginas.

```
docker network create microservicies
```

Copiaremos nuestas paginas web dentro de la carpeta de nginx **html**
Todo este proceso no se esta ejecutando detras de excesa en caso que lo requieras tu, adiciona la bandera -D (dispatch) este es su significado

```
docker run --rm -v ~/Documents/docker/index.html:/usr/share/nginx/html/index.html -P --network microservicies nginx
```

```
docker run --rm -v ~/Documents/docker/index2.html:/usr/share/nginx/html/index.html -P --network microservicies nginx
```

Finalmente copiaremos tambien nuestro fichero default.conf

```
docker run --rm -v ~/Documents/docker/default.conf:/etc/nginx/conf.d/default.conf -P --network microservicies nginx
```

Lo podremos visualizar usando el puerto que nos brinda docker del ultimo contenedor
