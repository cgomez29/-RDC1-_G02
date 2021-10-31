## TOPOLOGIA 1 (Cristian)
### Numero de hosts: 5
### Desglose
- Router: 5

### Red: 10.2.0.0/16
| Decimal | Binario   | Conversión |
| ------- | --------- | ---------- |
| 10      | 0000 1010 | 2+8 = 10   |
| 2       | 0000 0010 | 2 = 2      |
| 0       | 0000 0000 | 0 = 0      |
| 0       | 0000 0000 | 0 = 0      |

| Red               | Host              |
| ----------------- | ----------------- |
| 00001010 00000010 | 00000000 00000000 |

### Número de subredes
Se utilizarán 3 subredes, pues es el máximo de interfaces a usar en un solo router.

| Subred | Nombre |
| :----: | :----: |
|   1    |  Int1  |
|   2    |  Int2  |
|   3    |  Int3  |

### Cálculo de subnetting mediante FLSM
1. Identificar máscara actual: 11111111.11111111.00000000.00000000
2. Obtener número bits necesarios para los host: 2^2 = 4 >= 3; n = 2
3. Obtener nueva máscara: 11111111.11111111.**11**000000.00000000 (/18)
4. Obtener salto de red: 256-(128+64) = 256-192 = 64

| Salto | Network    | Mask          | P.D asignable | U.D asignable | Broadcast    | Host totales | Cantidad de host |
| :---: | ---------- | ------------- | ------------- | ------------- | ------------ | :----------: | :--------------: |
|  64   | 10.2.0.0   | 255.255.192.0 | 10.2.0.1      | 10.2.63.254   | 10.2.63.255  |    16382     |        5         |
|  64   | 10.2.64.0  | 255.255.192.0 | 10.2.64.1     | 10.2.127.254  | 10.2.127.255 |    16382     |        5         |
|  64   | 10.2.128.0 | 255.255.192.0 | 10.2.128.1    | 10.2.191.254  | 10.2.191.255 |    16382     |        5         |

### Direcciones
| Dispositivo | Direccion IP | Prefijo IP |
| ----------- | ------------ | :--------: |
| R3 int1     | 10.2.0.1     |    /18     |
| R3 int2     | 10.2.64.1    |    /18     |
| R3 int3     | 10.2.128.1   |    /18     |
| R4 int1     | 10.2.0.2     |    /18     |
| R4 int2     | 10.2.64.2    |    /18     |
| R4 int3     | 10.2.128.2   |    /18     |
| R5 int1     | 10.2.0.3     |    /18     |
| R5 int2     | 10.2.64.3    |    /18     |
| R5 int3     | 10.2.128.3   |    /18     |
| R6 int1     | 10.2.0.4     |    /18     |
| R6 int2     | 10.2.64.4    |    /18     |
| R6 int3     | 10.2.128.4   |    /18     |
| R7 int1     | 10.2.0.5     |    /18     |
| R7 int2     | 10.2.64.5    |    /18     |
| R7 int3     | 10.2.128.5   |    /18     |

## TOPOLOGIA 2 (Gustavo)
### Numero de hosts: 190
### Desglose
- Router: 1
- Recursos humanos: 21
- Contabilidad: 8
- Ventas: 93 + 93*(32/100) = 123
- Informatica: 31 + 31*(18/100) = 37

### Red: 192.168.42.0/24
| Decimal | Binario   | Conversión     |
| ------- | --------- | -------------- |
| 192     | 1100 0000 | 128+64 = 192   |
| 168     | 1010 1000 | 128+32+8 = 168 |
| 42      | 0010 1010 | 32+8+2 = 42    |
| 0       | 0000 0000 | 0 = 0          |

| Red                        | Host     |
| -------------------------- | -------- |
| 11000000 10101000 00110100 | 00000000 |

### Número de subredes
Se utilizará una subred por departamento, por lo que se necesitarán 4 subredes.

| Subred | Vlan  |     Nombre      |
| :----: | :---: | :-------------: |
|   1    |   -   | administradores |
|   2    |  10   |    rhumanos     |
|   3    |  20   |  contabilidad   |
|   4    |  30   |     ventas      |
|   5    |  40   |   informatica   |

### Cálculo de subnetting mediante VLSM
#### Ventas
1. Identificar máscara actual: 11111111.11111111.11111111.00000000
2. Obtener número de host: 2^7 - 2 = 126 >= 123; m = 7
3. Obtener nueva máscara: 11111111.11111111.**11111111.1**0000000 (/25)
4. Obtener salto de red: 256 - 128 = 128

#### Informática
1. Identificar máscara actual: 11111111.11111111.11111111.00000000
2. Obtener número de host: 2^6 - 2 = 62 >= 37; m = 6
3. Obtener nueva máscara: 11111111.11111111.**11111111.11**000000 (/26)
4. Obtener salto de red: 256 - 64 = 192

#### Recursos humanos
1. Identificar máscara actual: 11111111.11111111.11111111.00000000
2. Obtener número de host: 2^5 - 2 = 30 >= 21; m = 5
3. Obtener nueva máscara: 11111111.11111111.**11111111.111**00000 (/27)
4. Obtener salto de red: 256 - 32 = 224

#### Contabilidad
1. Identificar máscara actual: 11111111.11111111.11111111.00000000
2. Obtener número de host: 2^4 - 2 = 14 >= 8; m = 4
3. Obtener nueva máscara: 11111111.11111111.**11111111.1111**0000 (/28)
4. Obtener salto de red: 256 - 16 = 240

| VLAN  | Salto | Network        | Mask            | P.D asignable  | U.D asignable  | Broadcast      | Host totales | Cantidad de host |
| :---: | :---: | -------------- | --------------- | -------------- | -------------- | -------------- | :----------: | :--------------: |
|  30   |  128  | 192.168.42.0   | 255.255.255.128 | 192.168.42.1   | 192.168.42.126 | 192.168.42.127 |     126      |       123        |
|  40   |  192  | 192.168.42.128 | 255.255.255.192 | 192.168.42.129 | 192.168.42.190 | 192.168.42.191 |      62      |        37        |
|  10   |  224  | 192.168.42.192 | 255.255.255.224 | 192.168.42.193 | 192.168.42.222 | 192.168.42.223 |      30      |        21        |
|  20   |  240  | 192.168.42.224 | 255.255.255.240 | 192.168.42.225 | 192.168.42.238 | 192.168.42.239 |      14      |        8         |

### Direcciones
| Dispositivo      | Direccion IP   | Prefijo IP |
| ---------------- | -------------- | :--------: |
| R2 int1          | 192.168.42.1   |    /24     |
| R2 int2          | 192.168.42.2   |    /24     |
| R2 int3          | 192.168.42.3   |    /24     |
| VPC ventas       | 192.168.42.1   |    /25     |
| VPC ventas2      | 192.168.42.2   |    /25     |
| VPC informatica  | 192.168.42.129 |    /26     |
| VPC informatica2 | 192.168.42.130 |    /26     |
| VPC rrhh         | 192.168.42.193 |    /27     |
| VPC contabilidad | 192.168.42.225 |    /28     |

## TOPOLOGIA 3 (Daniel)
### Numero de hosts: 7
### Desglose
- Router: 1
- Administradores: 2
- Servidores contabilidad: 1
- Servidores recursos humanos: 1
- Servidores web: 1
- Servidores bases de datos: 1

### Red: 192.168.52.0/24
| Decimal | Binario   | Conversión     |
| ------- | --------- | -------------- |
| 192     | 1100 0000 | 128+64 = 192   |
| 168     | 1010 1000 | 128+32+8 = 168 |
| 52      | 0011 0100 | 32+16+4 = 52   |
| 0       | 0000 0000 | 0 = 0          |

| Red                        | Host     |
| -------------------------- | -------- |
| 11000000 10101000 00110100 | 00000000 |

### Número de subredes
Se utilizará una subred por cada departamento, y una subred para los administradores, por lo que se necesitarán 5 subredes.

| Subred | Vlan  |     Nombre      |
| :----: | :---: | :-------------: |
|   1    |   -   | administradores |
|   2    |  10   |    rhumanos     |
|   3    |  20   |  contabilidad   |
|   4    |  30   |     ventas      |
|   5    |  40   |   informatica   |

### Cálculo de subnetting mediante FLSM
1. Identificar máscara actual: 11111111.11111111.11111111.00000000
2. Obtener número bits necesarios para los host: 2^3 = 8 >= 5; n = 3
3. Obtener nueva máscara: 11111111.11111111.11111111.**111**00000 (/27)
4. Obtener salto de red: 256-(126+64+32) = 256-224 = 32

| VLAN  | Salto | Network        | Mask            | P.D asignable  | U.D asignable  | Broadcast      | Host totales | Cantidad de host |
| :---: | :---: | -------------- | --------------- | -------------- | -------------- | -------------- | :----------: | :--------------: |
|   -   |  32   | 192.168.52.0   | 255.255.255.224 | 192.168.52.1   | 192.168.52.30  | 192.168.52.31  |      30      |        2         |
|  10   |  32   | 192.168.52.32  | 255.255.255.224 | 192.168.52.33  | 192.168.52.62  | 192.168.52.63  |      30      |        1         |
|  20   |  32   | 192.168.52.64  | 255.255.255.224 | 192.168.52.65  | 192.168.52.94  | 192.168.52.95  |      30      |        1         |
|  30   |  32   | 192.168.52.96  | 255.255.255.224 | 192.168.52.97  | 192.168.52.126 | 192.168.52.127 |      30      |        1         |
|  40   |  32   | 192.168.52.128 | 255.255.255.224 | 192.168.52.129 | 192.168.52.158 | 192.168.52.159 |      30      |        1         |

### Direcciones
| Dispositivo | Direccion IP   | Prefijo IP |
| ----------- | -------------- | :--------: |
| R1 int1     | 192.168.52.34  |    /27     |
| R1 int2     | 192.168.52.66  |    /27     |
| R1 int3     | 192.168.52.98  |    /27     |
| VPC admin1  | 192.168.52.1   |    /27     |
| VPC admin2  | 192.168.52.2   |    /27     |
| srv_rrhh    | 192.168.52.33  |    /27     |
| srv_conta   | 192.168.52.65  |    /27     |
| srv_web     | 192.168.52.97  |    /27     |
| srv_bd      | 192.168.52.129 |    /27     |
