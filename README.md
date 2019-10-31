# Bitcoin Node for dummies
## Learn how to run a Bitcoin Node. Easy and fast ;)
Sabemos que correr un nodo de bitcoin puede sonar solo para desarrolladores Top Notch/hackers/phd, pero no es asi; cualquiera puede tener un nodo de bitcoin. 

### Our Version
Nuestro nodo esta corriendo en una laptop con las siguientes especificaciones:

-HP Envy 14, procesador iCore i5, 6 GB de Ram 
-External HDD 1TB (donde se almacena la blockchain)
-Ubuntu 18

### Clona el repositorio de Bitcoin
```
$ git clone https://github.com/bitcoin/bitcoin.git
$ cd bitcoin
```
### Selecciona la version mas reciente
```
$ git tag
v0.16.1
v0.17.2rc2
v0.18.0
v0.18.1
v0.18.1rc1
:...skipping...
```
Puedes consutar la version mas reciente y esatble en [Bitcoin Verison History](https://bitcoin.org/en/version-history)
```
$ git checkout v.018.1
$ git status
HEAD detached at V.018.1
nothing to commit working directory clean
```
### Instala las dependdencias necesarias
Dentro del directorio de Bitcoin se encuentra el directorio "doc". Accesa a el y lee el documento build-unix.md donde instalaras
las dependecias necesarias para compilar el Bitcoin Core en Ubuntu.
```
$ sudo apt-get install libssl-dev libevent-dev libboost-system-dev libboost-filesystem-dev libboost-chrono-dev libboost-test-dev libboost-thread-dev
```
## Configurando el Build Process

### Verifica las dependencias
```
$ ./autogen.sh
```
El script anterior verificarà que tengas las dependecias necesarias para que proceso de Build puede correr.
### Corre el script de configuaciòn
```
$ ./configure 
```
Antes de compilarlo, ejecuta el script anterior que verifica la librerias necesarias para compilar

## Compila el nodo

### Compila
```
$ make
```
Ejecutando el comando anterior, el Core empezarà a compilar. (El proceso puede tardar mas de una hora)
### Instala el nodo
```
$ make check && sudo make install
```
Este script ejecutarà un test e instalara el nodo.
una vez instalado ejecuta los siguientes comandos:
```
$ which bitcoind
/usr/local/bin/bitcoind

which bitcoin-cli
/usr/local/bin/bitcoin-cli
```
#### Tu Nodo de bitcoin ha sido instalado correctamente

## Configurando el nodo
### Especifica el almacenamiento de la blockchain y activa los index
Si corres el nodo tal y como està, la blockchain de Bitcoin se alojarà en el disco duro interno de tu equipo. Como nosotros queremos que se instale dentro del disco duro externo tendremos que modificar crearemos el archivo "bitcoin.conf y le pasaremos la ruta donde se encuentra nuestro disco duro.
Tambien le pasamos "txindex=1" para guarde todas los indexes y veamos la informacion detallada de cada transaccion a traves del la linea de comandos. 
```
datardir=/media/usr/externaldisc
txindex=1
```
## Corriendo el nodo
### Visualiza en consola
```
bitcoind -printtoconsole
``` 
Visualizaras la descarga y el proceso de tu nodo en la terminal
Tu nodo de bitcoin correra, 
### Bitcoin Daemon
```
bitcoind -daemon
```
Tu nodo correra en segundo plano y podras utilizar la linea de comandos, ademas podras hacer llamadas a traves de JSON RPC.


