### Universidad de San Carlos de Guatemala

### Facultad de Ingeniería

### Escuela de Ciencias y Sistemas

## Practica 2


<div>
    <p align="center">
       <img src="images/usac.png" width="500" alt="inicio"> 
  <p>
</div>

<hr>
<br>
<div>
    <table>
        <tr>
            <th>Nombre</th>
            <th>Carnet</th>
        </tr>
        <tr>
            <th>Cristian Daniel Raguay Vicente</th>
            <th>201603103</th>
        </tr>
        <tr>
            <th>Elmer Gustavo Sánchez García</th>
            <th>201801351</th>
        </tr>
        <tr>
            <th>Cristian Alexander Gomez Guzman</th>
            <th>201801480</th>
        </tr>
        <tr>
            <th>Pablo Fernando Cabrera Pineda</th>
            <th>201901698</th>
        </tr>
    </table>
</div>
<br>
<hr>

## Plataforma utilizada

<div>
    <p align="center">
       <img src="images/GoogleCloud.png" width="500" alt="inicio"> 
    <p>
</div>

## Software utlizado

## OpenVPN v3.3.1
<div>
    <p align="center">
       <img src="images/openvpn.png" width="500" alt="inicio"> 
    <p>
</div>

## GNS3 v2.2.22  
<div>
    <p align="center">
    <img src="images/gns3.png" width="500" alt="inicio"> 
    <p>
</div>

## VirtualBox v6.1 
<div>
    <p align="center">
    <img src="images/virtualbox.png" width="500" alt="inicio"> 
    <p>
</div>

# Configuración de máquina virtual 
## En la barra de herramientas seleccionamos 'Edit' luego Preferencias
<div>
    <p align="center">
    <img src="images/img10.PNG" width="500" alt="inicio"> 
    <p>
</div>

## Descargamos la máquina virtual de GNS3
<div>
    <p align="center">
    <img src="images/img21.PNG" width="500" alt="inicio"> 
    <p>
</div>

## Damos doble click sobre el archivo descargado 
<div>
    <p align="center">
    <img src="images/img22.PNG" width="500" alt="inicio"> 
    <p>
</div>

## Se nos desplegará un menú de nuestro virtualizador en este caso Virtual Box para importar la máquina virtual. El cual solo se debe de dar click en importar y listo la máquina virtual se agregará.
<div>
    <p align="center">
    <img src="images/img23.PNG" width="500" alt="inicio"> 
    <p>
</div>



## En preferencias seleccionamos nuestro virtualizador en este caso se utilizo VirtualBox 

- Seleccionamos Enable the GNS3 VM 
- Seleccionamos nuestra maquina 
- Dejamos el puerto 80 por defecto
- Ingresamos la cantidad de vCPUs  
- Ingresamos la cantidad de RAM 
- Seleccionamoes Keep the GNS3 VM runnig, esto si queremos que nuestra máquina se encienda cada vez que abramos GNS3

<div>
    <p align="center">
    <img src="images/img11.PNG" width="500" alt="inicio"> 
    <p>
</div>

- damos OK.

## Automaticamente nuestra máquina "vm" se iniciara.
<div>
    <p align="center">
    <img src="images/img15.PNG" width="500" alt="inicio"> 
    <p>
</div>

## Agregando una máquina virtual 
## En preferencias seleccionamos VirtualBox VMs 
- creamos una nueva

<div>
    <p align="center">
    <img src="images/img12.PNG" width="500" alt="inicio"> 
    <p>
</div>

- Damos siguiente

<div>
    <p align="center">
    <img src="images/img13.PNG" width="500" alt="inicio"> 
    <p>
</div>

- Seleccionamos la máquina virtual que deseamos agregar

- Seleccionamos Use as linked base VM
<div>
    <p align="center">
    <img src="images/img14.PNG" width="500" alt="inicio"> 
    <p>
</div>

- Y listo la máquina se encontrará disponible en: Browse end device (Dispositivos).


#  Configuración de las topologías 
## Topologia 1
- Las conexiones entre las Nubes y los switchs son enlaces truncales 

<div>
    <p align="center">
    <img src="images/img24.PNG" width="500" alt="inicio"> 
    <p>
</div>


## Topología 1
## Topologia 2
### Se cinfiguro las VLAN del switch para cada uno de los servidores la 10 para informatica en el puerto 0, la 20 para el area de Ventas en el puerto 1 y la 30 para el area de Contabilidad.
<div>
    <p align="center">
    <img src="images/topologia2-sw.JPG" width="500" alt="inicio"> 
    <p>
</div>

### Se configuro una conexion UDP para tener conexion con la topologia 1

<div>
    <p align="center">
    <img src="images/topologia2-udp.JPG" width="500" alt="inicio"> 
    <p>
</div>

### Topologia 2 Completa
<div>
    <p align="center">
    <img src="images/Tipologia2.JPG" width="500" alt="inicio"> 
    <p>
</div>

# Configuracíon VPCs
# Instalación y Configuración  de los servidores Web
### Lo primero que hay que hacer es actualisar el sistema operativo Linux con el comando.
```
sudo apt update
```

### Despues de Actualizar el sistema Linux se intala el Servidor Web Apache con el comando.
```
sudo apt install apache2
```
### En el navegador Web se escribe localhost y desplegara una la siguiente pagína como prueba de que se instalo apache correctamente.

<div>
    <p align="center">
    <img src="images/apache.JPG" width="500" alt="inicio"> 
    <p>
</div>

### Despues de intaloado apache no vamos a la carpera /var/www/html y ahi encontraremos un archivo html con nombre index.html que es la que trae por defecto apache, lo que vamos  a hacer es remplazar ese archivo con el que vamos a desplegar, este archivo tiene que tener el mismo nombre del archi eliminado para que se despliegue de manera correcta.
```
comando para eliminar
    sudo rm nombreArchivo
para crear un archivo
    sudo gedit index.html
para copiar un archivo ya listo para desplegar, debe de estar en la carpeta donde se encuentra el archivo a copiar
    cp nombreArchivo /direccion/destino
```

### Refrescamos el navegador de antes y veremos nuestra paguina desplegada

 <div>
    <p align="center">
    <img src="images/img_IServer.PNG" width="500" alt="inicio"> 
    <p>
</div>

# Visualización de la página web desde el host vrtual Cliente

## Cliente informatica 2

<div>
    <p align="center">
    <img src="images/img_IServer.PNG" width="500" alt="inicio"> 
    <p>
</div>

## Ping entre Maquinas Virtuales
### Servidor de Informatica con los clientes que son las ip 192.168.12.15 y ip 192.168.12.30 
<div>
    <p align="center">
    <img src="images/informatica.JPG" width="500" alt="inicio"> 
    <p>
</div>

### Servidor de Ventas con los clientes que son las ip 192.168.22.15 y ip 192.168.22.30
<div>
    <p align="center">
    <img src="images/Ventas.JPG" width="500" alt="inicio"> 
    <p>
</div>

### Servidor de Contabilidad con los clientes que son las ip 192.168.32.15 y ip 192.168.32.30
<div>
    <p align="center">
    <img src="images/Contabilidad.JPG" width="500" alt="inicio"> 
    <p>
</div>
