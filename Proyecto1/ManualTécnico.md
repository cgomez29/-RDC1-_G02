### Universidad de San Carlos de Guatemala

### Facultad de Ingeniería

### Escuela de Ciencias y Sistemas

## Manual Técnico


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


## **Índice**   
1. [Requerimientos](#id1)
2. [Comandos utilizados](#id2)
3. [IP](#id3)
4.  [Modo truncal](#id4)
5.  [VLAN](#id5)
6.  [Modo acceso](#id6)
7.  [VTP](#id7)
8.  [STP](#id8)
9.  [Ping entre departamentos](#id9)

<div id='id1' />

## Requerimientos 

### Software utilizado
* GNS3 v2.2.22 
* Open VPN

### Requerimientos minimos para usar GNS3
*   Procesador:  2 o mas núcleos lógicos
*   Virtualización:  Se requieren extensiones de virtualización. Es posible que deba habilitar esto a través del BIOS de su computadora.
*   4 GB RAM 
*   1 GB de espacio disponible




## Topologia 1: Área de Trabajo
## Topologia 2: Backbone 
## Topologia 3: Zona de Servidores

<br>
<br>

<div id='id2' />

## Comandos utilizados 

<div id='id3' />

# VPC 


### Configuración de una IP

```
    ip 192.168.X.X 255.255.255.0 192.168.X.X
```
### Comando para guardar las configuraciones

```
   save
```

<div id='id4' />

# Switchs 
### Comando para guardar las configuraciones

```
   write
```



## Configurando modo de truncal

```
    configure terminal
    int f#/# (ejemplo f1/1)
    Switchport mode trunk
    Switchport trunk allowed vlan 1,#vlan, 1002-1005
```

### Ejemplo

```
    configure terminal
    int f1/0
    switchport mode trunk
    switchport trunk allowed vlan 1-2,1002-1005,12,22,32,42

```

<br>

### Comando para vizualizar los puertos que estan en modo truncal

```
    show interfaces trunk
```
### ó

```
    show interfaces f#/# swichport
```

<div id='id5' />


## Crear vlan 

```
    configure terminal 
    vlan #
    name [name]
    end
```
### En donde # es el numero de la vlan a crear
### y [name] es nombre que la identificara.

<br>

### Comando para visualizar la configuración de la VLAN
```
    show vlan-sw
```
### ó
```
    vl
```

<br>

## Vlans creadas en el proyecto
### switch server vlan 12,22,32,42
```
    configure terminal
    vlan 12
    name rrhh
    vlan 22
    name informatica
    vlan 32
    name contabilidad
    vlan 42
    name ventas
    end 
    wr
``` 

<div id='id6' />


## Configurando modo de acceso


```
    configure terminal 
    interface f#/# 
    switchport mode access 
    switchport access vlan #vlan
```

### Ejemplo
```
    configure terminal 
    int f1/0
    switchport mode access
    switchport access allowed vlan 1-2,1002-1005,22
```

### Comando para verficar la correcta asignación del puerto en modo acceso
```
    show vlan-sw

```

<div id='id7' />

## Configurando VTP


```
    VTP
    conf t
    vtp domain [name}
    vtp password [password]
    vtp mode server/client/transparent
    sh vtp status


    VTP Pruning 
    conf t 
    vtp pruning
    end 

```

### Configuración del switch server

```
    VTP
    configure terminal
    vtp domain grupo2
    vtp grupo2
    vtp mode server
    end
```

### Configuración del switch client

```
    VTP
    configure terminal
    vtp domain grupo2
    vtp grupo2
    vtp mode client
    end
```

### VTP Pruning 

```
    conf t 
    vtp pruning
    end 

```


### Comando para visualizar la configuración del VTP
```
    show vtp status
```

<div id='id8' />


## Configuracion del Spannig Tree Protocol (STP)
### Sobre el switch server

```
    configure terminal
    spannig-tree vlan # root primary
```

### Ejemplo
```
    conf t
    spanning-tree vlan 12 root primary
```

## verificar el Switch root 
```
    show spannig-tree root
```
## Verificar STP 
```
    show spanning-tree brief
```

## Puertos bloqueados
```
    show spannig-tree blockedports
```
<div id='id9' />

# Pings entre departamentos

## Departamento de Recursos humanos
<div>
    <p align="center">
       <img src="images/Ping-RRHH1.PNG" width="500" alt="inicio"> 
    <p>
</div>

### Recursos humanos 2
<div>
    <p align="center">
       <img src="images/Ping-RRHH2.PNG" width="500" alt="inicio"> 
    <p>
</div>

### Servidor de recursos humanos
<div>
    <p align="center">
       <img src="images/Server_RRHH.PNG" width="500" alt="inicio"> 
    <p>
</div>


## Departamento de Informatica
### Informatica 1
<div>
    <p align="center">
       <img src="images/Ping-Informatica1.PNG" width="500" alt="inicio"> 
    <p>
</div>

### Informatica 2
<div>
    <p align="center">
       <img src="images/PING-Informatica2.jpg" width="500" alt="inicio"> 
    <p>
</div>

### Servidor de Informatica
<div>
    <p align="center">
       <img src="images/Server_Informatica.JPG" width="500" alt="inicio"> 
    <p>
</div>

## Departamento de Contabilidad
### Contabilidad 1
<div>
    <p align="center">
       <img src="images/Ping-Conta1.PNG" width="500" alt="inicio"> 
    <p>
</div>

### Contabilidad 2
<div>
    <p align="center">
       <img src="images/Ping-Conta2.PNG" width="500" alt="inicio"> 
    <p>
</div>

### Servidor de Contabilidad
<div>
    <p align="center">
       <img src="images/server_Conta.JPG" width="500" alt="inicio"> 
    <p>
</div>

## Departamento de Ventas

### Ventas 1
<div>
    <p align="center">
       <img src="images/Ping-Ventas1.PNG" width="500" alt="inicio"> 
    <p>
</div>

### Servidor de Ventas
<div>
    <p align="center">
       <img src="images/server_Ventas.JPG" width="500" alt="inicio"> 
    <p>
</div>

## Departamento de RRHH
### RRHH 1
<div>
    <p align="center">
       <img src="images/Ping-RRHH1.PNG" width="500" alt="inicio"> 
    <p>
</div>

### RRHH 2
<div>
    <p align="center">
       <img src="images/Ping-RRHH2.PNG" width="500" alt="inicio"> 
    <p>
</div>

### Servidro de RRHH
<div>
    <p align="center">
       <img src="images/Server_RRHH.PNG" width="500" alt="inicio"> 
    <p>
</div>
