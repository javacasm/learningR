¿qué es R?
R es un potente paquete de análisis numérico y estadístico. Es complemtante open-source

Instalar R en ubuntu

sudo apt-get install r-base

Unos 100Mb de instalación después podemos abrir la consola ejecutando 

	R

Podemos abrir la ayuda en un navegador con 
help.start()

## CookBook

* Salir de R

q()

* Cargar un fichero en formato csv
granada.data <- read.csv('user-data-Granada.csv',sep=';')

* Resumen de los datos

summary(granada.data)

* Para instalar un package (por ejemplo ggplot2 para hacer gráficos)

install.package("ggplot2")

Si no lo estamos ejecutando como root (lo cual está bien), nos preguntará si queremos utilizar un repositorio de paquetes local. Seleccionamos la carpeta (por defecto ~/R/) y se descargará el paquete, se compilará (no he probado lo que ocurre si no tenemos instalado el entorno de compilación) y ya podemos usarlo. [Más detalles](http://www.r-bloggers.com/installing-r-packages/)
