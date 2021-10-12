Configuración de la interfaz serial

conf t
int s3/1
ip address 172.23.0.1 255.255.0.0
no shutdown
exit

 Configuración de enlace

conf t
int f0/0
ip address 192.168.21.1 255.255.255.0
no shutdown
exit


Rutas estaticas
conf t
ip route 192.168.23.0 255.255.255.0 172.23.0.2
exit


sh ip int brief