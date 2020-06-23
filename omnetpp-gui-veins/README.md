# omnetp
Diturunkan dari janwtr/omnetpp-gui-sumo dan ditambahkan modul veins 5.0

## Docker command
```
> docker run --rm -it -e DISPLAY=192.168.1.8:0.0 janwtr/omnetpp-gui-veins:latest
```
### With volume
```
> docker run --rm -it -e DISPLAY=192.168.1.8:0.0 --mount type=bind,source=myveins,target=/root/models/veins 
janwtr/omnetpp-gui-veins:latest
```
