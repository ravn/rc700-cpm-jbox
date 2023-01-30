Downloaded files from http://www.jbox.dk/rc702/source/

ROA375.ROM is the RC702 prom.

To manually execute the relocate to $7000:

```
zsid roa.com
l70d0
f106,106,1
f10c,10c,1
f111,111,1
f123,123,1
g101,124
l70d0
```

The final list should show something along:

```
  70D0  LD   SP,BFFF
  70D3  LD   A,73
  70D5  LD   I,A  
  70D7  IM 2 
  70D9  LD   C,FF
```


REZ has the relocated ROA375 PROM in its correct location with these commands. 

```
rez
oae97
rroa.com
o4000
rroa.ctl
rroa.sym
l70d0

```

To save new state in REZ.COM use

```
sroa.ctl
sroa.sym

```

and exit with Ctrl-C.

