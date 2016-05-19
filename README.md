# linux-cheatsheet

###terminal shortcuts
- clear terminal ___Ctrl + Shift + L___
- clear prompt line ___Ctrl + u___

###check if tcp port is listening
```
netstat -anp | grep 8002
```

###find file by name
```
find ./ -name filename
```

###find in files
```
grep -rnw <dir> -e "<pattern>"
```

###archiving
- tar.gz with progress
```
tar -zcvf - <source> | pv > <destination.tar.gz>
```
- untar
```
tar -xvf yourfile.tar
```

###network
- track incomming HTTP traffic(works only for traffic from outside of localhost)
```
sudo tcpdump -s 0 -A -i en1 "tcp port $PORT and (((ip[2:2] - ((ip[0]&0xf)<<2)) - ((tcp[12]&0xf0)>>2)) != 0)"
```
