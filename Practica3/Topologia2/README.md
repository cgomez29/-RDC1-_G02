sw2
conf t
int range f1/1 - 3
channel-group 1 mode on
end
conf t
int range f1/4 - 6
channel-group 2 mode on
end

sw3
conf t
int range f1/1 - 3
channel-group 1 mode on
end
conf t
int range f1/4 - 6
channel-group 3 mode on
end

sw1
conf t
int range f1/1 - 3
channel-group 2 mode on
end
conf t
int range f1/4 - 6
channel-group 3 mode on
end
