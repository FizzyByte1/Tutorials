# Instalar Java JDK en Ubuntu
Antes de instalar Java JDK, se debe de tener el archivo tar.gz descargado en el sistema, para esto se puede acceder al siguiente enlace: [Java JDK 21](https://download.oracle.com/java/21/latest/jdk-21_linux-x64_bin.tar.gz).

Ó abrir una terminal y ejecutar el siguiente comando:

	wget https://download.oracle.com/java/21/latest/jdk-21_linux-x64_bin.tar.gz

Para instalar Java JDK, se creará una carpeta dentro del directorio /opt, donde se almacenaran la versión de Java que se desea instalar. Para ello, se ejecutara el siguiente comando en la terminal.

	sudo mkdir /opt/Java

Una vez creada la carpeta, se descomprimirá el archivo .tar.gz dentro de la carpeta creada.

	sudo tar -xvf jdk-21_linux-x64_bin.tar.gz -C /opt/Java

Ya descomprimido el archivo, se tiene que crear una variable de entorno dentro del sistema para que Java pueda ser ejecutado, para esto, primero habrá que abrir el archivo *.bashrc* este archivo contiene las configuraciones y variables de entorno individuales de cada usuario.

	sudo nano ~/.bashrc
		
Dentro de este archivo, al final, se agregará la siguiente configuración.

	JAVA_VERSION="jdk-21.0.1" #Corresponde al nombre de la carpeta que contiene Java dentro de la ruta /opt/Java
	export JAVA_HOME="/opt/Java/"$JAVA_VERSION
	export PATH=$PATH:$JAVA_HOME/bin

Una vez guardada la configuración, se tiene que volver a cargar el archivo para que esta sea detectada.

	. ~/.bashrc

Java ya se encontrará disponible en el sistema después de ejecutar esta configuración, para comprobar esto, se tiene que ejecutar el comando.

	java -version

Este comando mostrara la version actual instalada en el sistema.
