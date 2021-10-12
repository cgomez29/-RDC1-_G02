### ESW7
int range f1/0 - 2
channel-group 3 mode on

int range f1/3 - 5
channel-group 1 mode on

int port-channel 3
switchport mode trunk
switchport trunk allowed vlan 1,1002-1005

int port-channel 1
switchport mode trunk
switchport trunk allowed vlan 1,1002-1005


### ESW8
int range f1/0 - 2
channel-group 2 mode on

int range f1/3 - 5
channel-group 1 mode on

int port-channel 2
switchport mode trunk
switchport trunk allowed vlan 1,1002-1005

int port-channel 1
switchport mode trunk
switchport trunk allowed vlan 1,1002-1005


### ESW9
int range f1/0 - 2
channel-group 2 mode on

int range f1/3 - 5
channel-group 3 mode on

int port-channel 2
switchport mode trunk
switchport trunk allowed vlan 1,1002-1005

int port-channel 3
switchport mode trunk
switchport trunk allowed vlan 1,1002-1005
