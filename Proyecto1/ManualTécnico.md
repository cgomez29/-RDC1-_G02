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

## Requerimientos

* GNS3 v2.2.22 
* Open VPN


## Comandos utilizados

## VPC
### Configuración de una IP

```
    ip 192.168.X.X 255.255.255.0 192.168.X.X
```
### Comando para guardar las configuraciones

```
   save
```

## Switchs 
### Comando para guardar las configuraciones

```
   write
```

## Configurando modo de accesos


```
    configure terminal 
    interface f#/# 
    switchport mode access 
    switchport access vlan #vlan
    sh interfaces tr
```

## Configurando modo de truncal

```
    configure terminal
    int f#/# (ejemplo f1/1)
    Switchport mode trunk
    Switchport trunk allowed vlan 1,#vlan, 1002-1005
```

### Comando para vizualizar los puerto que estan en modo truncal

```
    show interfaces trunk
```
### ó

```
    show interfaces f#/# swichport
```

## Crear vlan 

```
    configure terminal 
    vlan #
    name ""
    end
```

### Comando para visualizar la configuración de la VLAN
```
    show vlan-sw
```
### ó
```
    vl
```

## Configurando VTP

```
    VTP
    conf t
    vtp domain Name
    vtp password
    vtp mode server/client/transparent
    sh vtp status


    VTP Pruning 
    conf t 
    vtp pruning
    end 

```

### Comando para visualizar la configuración del VTP
```
    show vtp status
```

## Configurar STP
```
    conf t
    spannig-tree brief
```
# verificar el Switch root 
```
    sh spannig-tree brief
```
# Verificar STP 
```
    show spanning-tree brief
```

# Puertos bloquados
```
    show spannig-tree blockedports
```