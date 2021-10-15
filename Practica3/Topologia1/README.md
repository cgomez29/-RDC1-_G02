## Topología 1
### Configuración del port-channel en el switch 1

```console
conf t
int range f1/1 - 3
channel-group 2 mode on
end
conf t
int range f1/4 - 6
channel-group 3 mode on
end
```
### Configuración del port-channel en el switch 2
```console
conf t
int range f1/0 - 2
channel-group 2 mode on
end
conf t
int range f1/3 - 5
channel-group 1 mode on
end
```
### Configuración del port-channel en el switch 3
```console
conf t
int range f1/3 - 5
channel-group 1 mode on
end
conf t
int range f1/0 - 2
channel-group 3 mode on
end
```
