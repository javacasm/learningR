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

