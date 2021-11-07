## R3

```console
	conf t
	int f0/0
	ip address 10.2.0.1 255.255.255.248
	no shutdown
	exit
	int f1/0
	ip address 10.2.0.9 255.255.255.248
	no shutdown
	exit
	int f2/0
	ip address 10.2.0.17 255.255.255.248
	no shutdown
	exit

```

## R4

```console
	conf t
	int f0/0
	ip address 10.2.0.2 255.255.255.248
	no shutdown
	exit
	int f1/0
	ip address 10.2.0.10 255.255.255.248
	no shutdown
	exit
```

## R5

```console
	conf t
	int f0/0
	ip address 10.2.0.3 255.255.255.248
	no shutdown
	exit
	int f1/0
	ip address 10.2.0.11 255.255.255.248
	no shutdown
	exit
	int f2/0
	ip address 10.2.0.33 255.255.255.248
	no shutdown
	exit
```

## R6

```console
    conf t
	int f0/0
	ip address 10.2.0.4 255.255.255.248
	no shutdown
	exit
	int f1/0
	ip address 10.2.0.25 255.255.255.248
	no shutdown
	exit
```

## R7

```console
    conf t
	int f0/0
	ip address 10.2.0.12 255.255.255.248
	no shutdown
	exit
	int f1/0
	ip address 10.2.0.41 255.255.255.248
	no shutdown
	exit

```

### RIPv2

## R3

```console
	conf t 
	router rip
	version 2
	network 10.2.0.8
	network 10.2.0.16
	network 10.2.0.0
	end 
	sh ip route
```

## R4

```console
	conf t 
	router rip
	version 2
	network 10.2.0.0
	network 10.2.0.8
	end 
	sh ip route
```

## R5

```console
	conf t 
	router rip
	version 2
	network 10.2.0.32
	network 10.2.0.0
	network 10.2.0.8
	end 
	sh ip route
```

## R6

```console
	conf t 
	router rip
	version 2
	network 10.2.0.0
	network 10.2.0.24
	end 
	sh ip route
```

## R7

```console
	conf t 
	router rip
	version 2
	network 10.2.0.8
	network 10.2.0.40
	end 
	sh ip route
```