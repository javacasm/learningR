¿qué es R?
R es un potente paquete de análisis numérico y estadístico. Es complemtante open-source

Instalar R en ubuntu

sudo apt-get install r-base

Unos 100Mb de instalación después podemos abrir la consola ejecutando 

	R

Podemos abrir la ayuda en un navegador con 
help.start()

## CookBook

* **q()** Salir de R

* Cargar un fichero en formato csv
granada.data <- read.csv('user-data-Granada.csv',sep=';')

* **summary(granada.data)** Resumen de los datos



* Para instalar un package (por ejemplo ggplot2 para hacer gráficos)

	install.package("ggplot2")

Si no lo estamos ejecutando como root (lo cual está bien), nos preguntará si queremos utilizar un repositorio de paquetes local. Seleccionamos la carpeta (por defecto ~/R/) y se descargará el paquete, se compilará (no he probado lo que ocurre si no tenemos instalado el entorno de compilación) y ya podemos usarlo. [Más detalles](http://www.r-bloggers.com/installing-r-packages/)

* **objects()**  muestra los datasets disponibles

* Nos referimos a una columna de un dataset con **dataset$columna** (como lo haríamos en excel, upsss )

* Cuando lo usamos se genera un fichero llamado **.Rhistory** con los distintos comandos, y ¿ cuando abrimos R desde una carpeta con un fichero así tenemos accesible  el histórico de comandos

* Si usamos **plot(dataset)** se representan todos los gráficos posibles de cada columna con todas las demas. En la diagonal aparecen los nombres de esa columna/fila

* Para representar un gráfico hacemos **plot(dataset$columanY,dataset$columnaY)** donde podemos usar cualquier operación matemática

* Podemos añadir una columna sin más que utilizar **dataset$NuevaColumna<-funcion(otros datos)** . Por ejemplo

	 granada.data$orderScaled<-seq_along(granada.data$contributions)/length(granada.data$contributions)

* **scale(x)** devuelve una columna con los valores centrados en la media [scale](https://stat.ethz.ch/R-manual/R-patched/library/base/html/scale.html)

* Para normalizar una columna al rango 0,1 hacemos [fuente](http://stackoverflow.com/questions/15468866/scaling-a-numeric-matrix-in-r-with-values-0-to-1):

	apply(m, MARGIN = 2, FUN = function(X) (X - min(X))/diff(range(X)))

* Para normalizar una columna que es una secuencia entre 1 y n basta con hacer

	granada.data$orderScaled<-seq_along(granada.data$contributions)/length(granada.data$contributions)

* Exportar ** write.csv(dataset, "filename.csv") ** para formato csv o ** write.table(dataset, "filename.txt, sep="\t") ** para exportar a otro formato

* Podemos hacer una **regresión lineal** (linear model) usando ** lm(waiting ~ duration) ** y representar la línea con abline(lm(waiting ~ duration)) (no me funciona!!) [detalles](http://msenux.redwoods.edu/math/R/regression.php)

* Para guardar una imagen podemos hacer ggsave("image.png")

* Para usar una librería haremos ** library("ggplot2") ** lo que nos permitirá usar nuevos métodos

* Para incluir varias series de puntos: 

	qplot(zaragoza.data$orderScaled,log10(zaragoza.data$contributions)) + 
	geom_point(aes(y=log10(almeria.data$contributions),x=almeria.data$orderScaled,color='almeria.data$contributions')) 