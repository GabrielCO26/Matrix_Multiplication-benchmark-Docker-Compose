# Matrix_Multiplication-benchmark-Docker-Compose

## Integrantes del grupo
* Gabriel Castro
* Jhon Minotta

## Ejecución
Para realizar el benchmark, en primera instancia se debe hacer git clone de este repositorio con: <br/>
`git clone https://github.com/GabrielCO26/Matrix_Multiplication-benchmark-Docker-Compose.git`

y levantar el contenedor (únicamente hay un servicio en el docker compose) con el comando: <br/>
`docker compose up`

el contenedor ejecutará una serie de comandos desde la terminal (internamente), que a grandes rasgos: <br/>
* Clona el repositorio con los códigos del benchmark
* Hace pull de cada una de las imagenes necesarias
* Corre cada uno de los contenedores que ejecutan los códigos, las imagenes utilizadas son las del anterior paso
* Los resultados de la ejecución de cada uno de los contenedores son guardados en diferentes arhcivos y son copiados a un único archivo de texto con nombre "resultados.txt"
* Borra el repositorio clonado y la carpeta de resultados, quedando únicamente el archivo resultados.txt que fue movido previamente al directorio en el que fue montado el volumen
* Borra todas las imagenes de los contenedores

El archivo con los resultados es traido ala carpeta donde se ejecutó el `docker compose up` desde el local, para visualizarlos se ejecuta el comando `cat resultados.txt` y este tendrá un formato:
```
Python: (time) ms
JavaScript: (time) ms
C++: (time) ms
Java: (time) ms
Rust: (time) ms
```

## Enlaces al repositorio
Enlace al repositorio desde el cual se hace "docker pull" de las imagenes: https://hub.docker.com/r/gacoco/activity2/tags

Enlace al respositorio con los códigos del benchmark: https://github.com/GabrielCO26/Matrix_Multiplication-benchmark
