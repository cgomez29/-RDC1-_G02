### Universidad de San Carlos de Guatemala

### Facultad de Ingeniería

### Escuela de Ciencias y Sistemas

<p align="center"><h2>Práctica 1</h2></p>

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


## Nuevo proyecto

### Creamos nuestro proyecto, ingresamos el nombre y si deseamos podemos modificar el ID.

<div>
    <p align="center">
       <img src="images/imagen1.PNG" width="500" alt="inicio"> 
    <p>
</div>

### Seleccionamos el proyecto que se acaba de crear.

<div>
    <p align="center">
       <img src="images/imagen2.PNG" width="500" alt="inicio"> 
    <p>
</div>

## IAM y ADMIN
### Agregamos y seleccionamos el rol que tendran nuestros compañeros de equipo en este caso se les otorgo el acceso completo.

<div>
    <p align="center">
       <img src="images/imagen3.PNG" width="500" alt="inicio"> 
    <p>
</div>

## Compute Engine
### Seleccionamos VM Instances.
<div>
    <p align="center">
       <img src="images/imagen4.PNG" width="500" alt="inicio"> 
    <p>
</div>

## Creamos una instancia

<div>
    <p align="center">
       <img src="images/imagen6.PNG" width="500" alt="inicio"> 
    <p>
</div>

### Ingresamos un nombre y seleccionamos el tipo de maquina que deseamos.

<div>
    <p align="center">
       <img src="images/imagen7-8.PNG" width="500" alt="inicio"> 
    <p>
</div>

### podemos elegir el sistemas operativo en este caso se utilizara Debian y seleccionamos en el apartado de Firewall el acceso por HTTP y HTTPS.
    

<div>
    <p align="center">
       <img src="images/imagen7y8.PNG" width="500" alt="inicio"> 
    <p>
</div>

## Instancia VM

### Después de seguir los pasos anteriores se puede observar que se creó satisfactoriamente la máquina virtual (VM). Se tiene que revisar que este la IP interna y la IP externa aparezcan en la instancia de la maquina virtual. Se presiona el boton de SSH para que se pueda proceder con el pasos siguientes.

```console
    Internal IP: 10.128.0.2
    External IP: 34.125.203.174
```

<div>
    <p align="center">
       <img src="images/imagen9.PNG" width="500" alt="inicio"> 
    </p>
</div>

## Cliente SSH

### Esta venta ventana emergente es un cliente SSH de Google que sirve para manejar la máquina virtual. Luego se procede a escribir el comando para poder actualizar los repositorios del sistema operativo (Debian) este proceso tarda unos minutos dependiendo de las especificaciones de la máquina virtual.

```console
    ~$: sudo apt-get update
```

<div>
    <p align="center">
       <img src="images/imagen10.PNG" width="500" alt="inicio"> 
    </p>
</div>

## Instalar WGET

### Luego de actualizar los repositorios, se procede a instalar el comando de **wget**. La funcionalidad de **wget** es que permita la descarga de contenido desde servidores web de una forma simple.

```console
    ~$: sudo apt-get install wget
```

<div>
    <p align="center">
       <img src="images/imagen11.PNG" width="500" alt="inicio"> 
    </p>
</div>

## Comando WGET

### Ahora que se tiene instalado wget, se procede con el comando más **importante**, lo que hace es descargar un archivo con extension _.sh_ de la página [cubaelectronica](www.cubaelectronica.com) y despues ejecuta el archivo descargado.

```console
    ~$: sudo wget https://cubaelectronica.com/OpenVPN/openvpn-install.sh
    ~$: sudo bash openvpn-install.sh
```

<div>
    <p align="center">
       <img src="images/imagen12.PNG" width="500" alt="inicio"> 
    </p>
</div>

## Manejador Openvpn

### En esta parte del consola se le pide ingresa la dirección IP interna, pero el openvpn ya la pone por defecto entonces es de verificar que sea la misma.

```console
    IP address: 10.182.0.2
```

<div>
    <p align="center">
       <img src="images/imagen13.PNG" width="500" alt="inicio"> 
    </p>
</div>

## IP Pública

### En esta parte se solicita que ingrese la dirección publica que es la que va salir hacia internet, entonces se revisa en la instancia VM, se copia la IP externa y se coloca en la consola.

```console
    Direccion IP Pública / o hostaname: 34.125.203.174
```

<div>
    <p align="center">
       <img src="images/imagen14.PNG" width="500" alt="inicio"> 
    </p>
</div>

## Protocolo

### Se pregunta que protocolo desea utilizar, lo más recomendado es utilizar el protocolo **UDP**. Es un protocolo de la capa de transporte encargado del intercambio de datagramas.

```console
    Protocolo [1-2]: 1
```

<div>
    <p align="center">
       <img src="images/imagen15.PNG" width="500" alt="inicio"> 
    </p>
</div>

## Puerto

### Que puerto escuchará OpenVPN, se utiliza el que es por defecto para el protocolo UDP.

```console
    Puerto: 1194
```

<div>
    <p align="center">
       <img src="images/imagen16.PNG" width="500" alt="inicio"> 
    </p>
</div>
