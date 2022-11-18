# Examen

## Introducción
Esta memoria va a redactar el proceso de trabajo en el examen de la asignatura de despliegue de aplciaciones web, iré por pasos explicando mi trabajo realizado y su proceso, y al final redactaré una conclusión.

## Índice

* Palabras clave
* Contexto
* Ejercicios
* Conclusión
* Bibliografía

## Palabras clave
Algunas palabras clave que iré usando a lo largo de este escrito son:  
  comando, directorio, terminal, máquina, apache, hosts virtuales.
  
## Contexto
En el examen de hoy de despliegue de aplciaciones web tenemos que redactar una memoria que contenga todo lo que hemos realizado a lo largo del examen.

## Ejercicios

* **Ejercicio 2**

Lo primero que hacemos es abrir la terminal y con los datos necesarios y el siguiente comando entramos en la máquina
```
$ ssh nombre_usuario@ip_usuario_remoto
```

Una vez dentro tenemos que crear un directorio con nuestro nombre en la dirección /var/www con el comando 
```
$ sudo mkdir /var/www/manuel
```

El problema es que al principio no encontraba el directorio /var/www y no podia crear mi directorio por lo tanto buscando, al final he usado el comando
```
$ cd -- 
```
hasta volver al directorio inicial y una vez allí si que he podido crear mi directorio.

Una vez dentro ejecutamos el comando
```
$ sudo touch ejercicio2.txt
```
para crear nuestro archivo .txt y finalizar este ejercicio. 

* **Ejercicio 3**

En este ejercicio seguimos dentro de la máquina y nos metemos en el direcotorio que hemos creado antes con el comando 
```
$ cd nombre_directorio
```
una vez dentro para descargar la imagen usaremos el comando 
```
$ sudo curl -O https://iesalandalus.org/ciclos/semipresencial/daw-sp/daw.png
```
y así terminaremos este ejercicio.

* **Ejercicio 4**

En este ejercicio trabajamos en nuestro ordenador por lo que tendremos que salir de la máquina usando el comando 
```
$ exit
```
de esta manera estaremos de nuevo en nuestro ondenador.

Lo primero que tendriamos que hacer es instalar apache pero como lo teniamos instalado previamente no nos hace falta volver a hacerlo. Entonces lo que vamos a hacer es crearnos un directorio como en el ejercicio 2
```
$ sudo mkdir /var/www/ejercicio4
```
Después, dentro de este directorio creamos un index.html con 
```
$ sudo nano index.html
```
Y lo modificamos poniendo lo que queremos que aparezca en nuestra página web
```
</html>
  <head>
    <title> Título de mi increible pagina </title>
  </head>
  <body>
    <p>Manuel Maratrat Pons</p>
  </body>
</html>
```
Seguiremos usando el comando
```
$ cd /etc/apache2/sites-available/
```
para movernos de directorio y usaremos el comando
```
$ sudo cp 000-default.conf ejercicio4.conf
```
para crear el .conf que nos servirá para darle el nombre a nuestra página web, para eso usaremos el comando 
```
$ sudo gedit ejercicio4.conf
```
Modificaremos DocumentRoot /var/www/nombre_directorio, poniendo el nombre del directorio que hemos creado antes y añadiremos ServerName daw.ejercicio4.com

Una vez hecho esto tendremos que activar el archivo de hosts virtuales
```
$ systemctl reload apache2
$ sudo a2ensite ejercicio4.conf
```

Una vez hecho esto iremos a hosts
```
$ sudo gedit /etc/hosts
```
Y añadiremos la linea 127.0.0.1 daw.ejercicio4.com

Una vez hechos todos estos pasos pondremos en nuestro buscador la dirección que tenemos y comprobaremos que nos funciona.

## Conclusión
Para poder hacer este exámen tenias que venir con las ideas claras y con los conceptos que hemos visto en clase claros también. Algun ejercicio era más sencillo de sacar que otro si sabías donde buscar, aunque en general si has seguido el ritmo de clase y has trabajado lo que debías el examen deberías poder aprobarlo. Aunque no era fácil no me ha parecido muy dificl, se acoplaba a los conocimientos adquiridos a lo largo del curso.

## Bibliografía
La mayor parte proviene de mis apuntes hechos en clase.  
[https://ubunlog.com/descargar-archivos-desde-terminal-ubuntu/](https://ubunlog.com/descargar-archivos-desde-terminal-ubuntu/)  
[https://markdown.es/sintaxis-markdown/](https://markdown.es/sintaxis-markdown/)
