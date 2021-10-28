## TOPOLOGIA 1 (Cristian)
### Red: 10.2.0.0/16
### Numero de hosts: 5
### Desglose
- Router: 5

### Cálculo de subnetting mediante FLSM
1. Identificar numero de subredes: 5
2. Identificar máscara actual: 11111111.11111111.00000000.00000000
3. Obtener número bits necesarios para los host: 2^n >= 5; 2^3 = 8 >= 5; n = 3
4. Obtener nueva máscara: 11111111.11111111.**111**00000.00000000 (/19)

| Salto | Network    | Mask          | P.D asignable | U.D asignable | Broadcast    | Host totales | Cantidad de host |
| :---: | ---------- | ------------- | ------------- | ------------- | ------------ | :----------: | :--------------: |
|  32   | 10.2.0.0   | 255.255.224.0 | 10.2.0.1      | 10.2.31.254   | 10.2.31.255  |     8190     |        1         |
|  32   | 10.2.32.0  | 255.255.224.0 | 10.2.32.1     | 10.2.63.254   | 10.2.63.255  |     8190     |        1         |
|  32   | 10.2.64.0  | 255.255.224.0 | 10.2.64.1     | 10.2.95.254   | 10.2.95.255  |     8190     |        1         |
|  32   | 10.2.96.0  | 255.255.224.0 | 10.2.96.1     | 10.2.127.254  | 10.2.127.255 |     8190     |        1         |
|  32   | 10.2.128.0 | 255.255.224.0 | 10.2.128.1    | 10.2.159.254  | 10.2.159.255 |     8190     |        1         |

### Direcciones
| Dispositivo | Direccion IP | Prefijo IP |
| ----------- | ------------ | :--------: |
| R3          | 10.2.0.1     |    /19     |
| R4          | 10.2.32.1    |    /19     |
| R5          | 10.2.64.1    |    /19     |
| R6          | 10.2.96.1    |    /19     |
| R7          | 10.2.128.1   |    /19     |

## TOPOLOGIA 2 (Gustavo)
### Red: 192.168.42.0/24
### Numero de hosts: 190
### Desglose
- Router: 1
- Recursos humanos: 21
- Contabilidad: 8
- Ventas: 93 + 93*(32/100) = 123
- Informatica: 31 + 31*(18/100) = 37

### Cálculo de subnetting mediante VLSM
#### Ventas
1. Identificar máscara actual: 11111111.11111111.11111111.00000000
2. Obtener número de host: 2^m - 2 >= 123; 2^7 - 2 = 126 >= 123; m = 7
3. Obtener nueva máscara: 11111111.11111111.**11111111.1**0000000 (/25)
4. Obtener salto de red: 256 - 128 = 128

#### Informática
1. Identificar máscara actual: 11111111.11111111.11111111.00000000
2. Obtener número de host: 2^m - 2 >= 37; 2^6 - 2 = 62 >= 37; m = 6
3. Obtener nueva máscara: 11111111.11111111.**11111111.11**000000 (/26)
4. Obtener salto de red: 256 - 64 = 192

#### Recursos humanos
1. Identificar máscara actual: 11111111.11111111.11111111.00000000
2. Obtener número de host: 2^m - 2 >= 21; 2^5 - 2 = 30 >= 21; m = 5
3. Obtener nueva máscara: 11111111.11111111.**11111111.111**00000 (/27)
4. Obtener salto de red: 256 - 32 = 224

#### Contabilidad
1. Identificar máscara actual: 11111111.11111111.11111111.00000000
2. Obtener número de host: 2^m - 2 >= 8; 2^4 - 2 = 14 >= 8; m = 4
3. Obtener nueva máscara: 11111111.11111111.**11111111.1111**0000 (/28)
4. Obtener salto de red: 256 - 16 = 240

| VLAN              | Salto | Network        | Mask            | P.D asignable  | U.D asignable  | Broadcast      | Host totales | Cantidad de host |
| ----------------- | :---: | -------------- | --------------- | -------------- | -------------- | -------------- | :----------: | :--------------: |
| 30 (ventas)       |  128  | 192.168.42.0   | 255.255.255.128 | 192.168.42.1   | 192.168.42.126 | 192.168.42.127 |     126      |       123        |
| 40 (informatica)  |  192  | 192.168.42.128 | 255.255.255.192 | 192.168.42.129 | 192.168.42.190 | 192.168.42.191 |      62      |        37        |
| 10 (rhumanos)     |  224  | 192.168.42.192 | 255.255.255.224 | 192.168.42.193 | 192.168.42.222 | 192.168.42.223 |      30      |        21        |
| 20 (contabilidad) |  240  | 192.168.42.224 | 255.255.255.240 | 192.168.42.225 | 192.168.42.238 | 192.168.42.239 |      14      |        8         |

### Direcciones
| Dispositivo      | Direccion IP   | Prefijo IP |
| ---------------- | -------------- | :--------: |
| R2               | 192.168.42.1   |    /24     |
| VPC ventas       | 192.168.42.1   |    /25     |
| VPC ventas2      | 192.168.42.2   |    /25     |
| VPC informatica  | 192.168.42.129 |    /26     |
| VPC informatica2 | 192.168.42.130 |    /26     |
| VPC rrhh         | 192.168.42.193 |    /27     |
| VPC contabilidad | 192.168.42.225 |    /28     |

## TOPOLOGIA 3 (Daniel)
### Red: 192.168.52.0/24
### Numero de hosts: 7
### Desglose
- Router: 1
- Administradores: 2
- Servidores contabilidad: 1
- Servidores recursos humanos: 1
- Servidores web: 1
- Servidores bases de datos: 1

### Cálculo de subnetting mediante FLSM
1. Identificar numero de subredes: 5
2. Identificar máscara actual: 11111111.11111111.11111111.00000000
3. Obtener número bits necesarios para los host: 2^n >= 5; 2^3 = 8 >= 5; n = 3
4. Obtener nueva máscara: 11111111.11111111.11111111.**111**00000 (/27)

| VLAN                 | Salto | Network        | Mask            | P.D asignable  | U.D asignable  | Broadcast      | Host totales | Cantidad de host |
| -------------------- | :---: | -------------- | --------------- | -------------- | -------------- | -------------- | :----------: | :--------------: |
| -  (administradores) |  32   | 192.168.52.0   | 255.255.255.224 | 192.168.52.1   | 192.168.52.30  | 192.168.52.31  |      30      |        2         |
| 10 (rhumanos)        |  32   | 192.168.52.32  | 255.255.255.224 | 192.168.52.33  | 192.168.52.62  | 192.168.52.63  |      30      |        1         |
| 20 (contabilidad)    |  32   | 192.168.52.64  | 255.255.255.224 | 192.168.52.65  | 192.168.52.94  | 192.168.52.95  |      30      |        1         |
| 30 (ventas)          |  32   | 192.168.52.96  | 255.255.255.224 | 192.168.52.97  | 192.168.52.126 | 192.168.52.127 |      30      |        1         |
| 40 (informatica)     |  32   | 192.168.52.128 | 255.255.255.224 | 192.168.52.129 | 192.168.52.158 | 192.168.52.159 |      30      |        1         |

### Direcciones
| Dispositivo | Direccion IP   | Prefijo IP |
| ----------- | -------------- | :--------: |
| R1          | 192.168.52.1   |    /24     |
| VPC admin1  | 192.168.52.1   |    /27     |
| VPC admin2  | 192.168.52.2   |    /27     |
| srv_rrhh    | 192.168.52.33  |    /27     |
| srv_conta   | 192.168.52.65  |    /27     |
| srv_web     | 192.168.52.97  |    /27     |
| srv_bd      | 192.168.52.129 |    /27     |
