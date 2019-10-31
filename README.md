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
Puedes consutar la version mas reciente y esatble en [Bitcoin Verison History](bitcoin.org/en/version-history)
```
$ git checkout v.018.1
$ git status
HEAD detached at V.018.1
nothing to commit working directory clean
```
### Instala las dependdencias necesarias
Dentro del directorio de Bitcoin se encuentra el directorio "depends". Accesa a el y lee el documento Readme.md donde instalaras
las dependecias necesarias para compilar el Bitcoin Core (Aqui instalaremos las necesarias para Ubuntu)
```
$ sudo apt-get install libssl-dev libevent-dev libboost-system-dev libboost-filesystem-dev libboost-chrono-dev libboost-test-dev libboost-thread-dev
```



