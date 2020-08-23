# ECMes: Extractor de Conocimiento Mejorado en Español 
* Método de extracción de relaciones semánticas para la Web (OIE) en español
* Open Information extraction method for Spanish language

## Instrucciones en español

### Pasos para compilar ECMes como aplicación

    1. Se necesita Java 1.8 or superior instalado junto con Maven (https://maven.apache.org/install.html). (probado con maven 3.5.2 y 3.3.9)
    
 		mvn clean compile assembly:single

	Este paso descargará todas las bibliotecas necesarias y luego construirá ECMes a partir del código fuente.
    2. Cuando termine, debería ver un mensaje con las palabras "BUILD SUCCESS" similar al siguiente:
	[INFO] --------------
	[INFO] BUILD SUCCESS
	[INFO] --------------

    3. La aplicación debe crearse en el directorio "target". Mueva el archivo jar al directorio padre y cámbiele el nombre a "ECMes.jar", puede hacerlo ejecutando el siguiente comando:

	mv target/ECMes-1.0-jar-with-dependencies.jar ECMes.jar
	
### Pasos para ejecutar ECMes

    1. En un ambiente Linux podrá ejecutarlo con el comando:  “runECMes.sh”, las opciones disponibles son:

	 -f  <file>: parametro obligatorio, indica un archivo de texto de entrada
	 -o  <file>: indica cual será el  archivo de salida. Si no está presente se muestra la salida por pantalla
	 -score : imprime el puntaje que tiene la extracción
	 -full : imprime el puntaje, el id, y si la relación es de tipo no-factica, indica su dependencia
	 -scoreLimitOff : ignora el limite de score para mostrar una relación extraida. El limite es: 1
	 -swne <file> : imprime en el archivo indicado las oraciones para las cuales no extrajo relaciones
	 -help : imprime este menú


	un ejemplo de ejecución sería:

	./runECMes.sh -f testFile.txt -full -o out.txt


    2. Si está en un entorno Windows u en otro SO, debe ejecutar la aplicación con el siguiente comando:

	java -jar -Xmx4056m  -Xms1024m -ea ECMes.jar 

	los parametros son los mismos, por ejemplo:

	java -jar -Xmx4056m  -Xms1024m -ea ECMes.jar -f testFile.txt -full

## English instructions

### Steps to cmpile ECMes as application

    1. user must have Java 1.8 or greater installed and Maven (https://maven.apache.org/install.html). (tested with maven 3.5.2 and 3.3.9)
    
 		mvn clean compile assembly:single

	This step will download all needed libraries and then will build ECMes from source code.
    2. When finish you should see a “BUILD SUCCESS” message similar to the following:
	[INFO] --------------
	[INFO] BUILD SUCCESS
	[INFO] --------------

    3. The application should be created into “target” directory. Please move the jar file to the parent directory and rename as ECMes.jar”, you can do that executing the following command:

	mv target/ECMes-1.0-jar-with-dependencies.jar ECMes.jar
	
### Steps to run ECMes

    1. If you are in a Linux environment, you can execute the file “runECMes.sh”, the available options are:

	 -f : mandatory parameter, indicates the input text file
	 -o : indicates the output file. If not present, the result will be printed in console	 
	 -score : also prints the score of the extraction
	 -full : prints score, id, and if the relation is non factual its dependency
	 -help : prints a help menu

	for example, you can execute:

	./runECMes.sh -f testFile.txt -full -o out.txt


    2. If you are under Windows environment or another SO, you must run the application with the following command:

	java -jar -Xmx4056m  -Xms1024m -ea ECMes.jar 

	the parameters are the same, for example:

	java -jar -Xmx4056m  -Xms1024m -ea ECMes.jar -f testFile.txt -full

