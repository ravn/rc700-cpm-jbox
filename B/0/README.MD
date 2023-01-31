Downloaded files from http://www.jbox.dk/rc702/source/

# Documentation

Z80 book: http://www.z80.info/zip/programming_the_z80_3rd_edition.pdf

Z80ASM manual:  https://oldcomputers.dyndns.org/public/pub/manuals/z80asm.pdf


# RC702 boot prom

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


REZ has the relocated ROA375 PROM in its correct location with these commands.   (The AE97 offset is because the boot prom starts moving its payload from to $7000 and then jumps to $70D0)

```
rez
oae97
rroa.com
o4000
rroa375b.ctl
rroa375b.sym
l70d0

```

To save new state and an updated assembly file, use

```
sroa375b.ctl
sroa375b.sym
sroa375b.asm
ql7000,7795
z

```

and exit with Ctrl-C.

For the "move boot loader payload and jump" bit use:

```
rez
o4000
rroa.com
o4100
rroa375a.ctl
rroa375a.sym
l0

```

and

```
sroa375a.ctl
sroa375a.sym
sroa375a.asm
l0,27
z

```

# CONFI - configuration utility

Original is in CONFIORG.COM.  Note:  This is one I appear to have patched back then for a better US-keyboard.

Old, almost complete disassembly in CONFI.Z80 (using Z80ASM instead of M80)

```
z80asm confi/fxs
```
(cannot generate symbol file)

RASM (https://github.com/EdouardBERGE/rasm) assembles but it is unclear how to create symbol file for ZSID. 

```
cp ~/git/RunCPM/RunCPM/C/0/CONFI.Z80 . ; ../rasm -ob CONFI.COM CONFI.Z80; diff CONFIORG.COM CONFI.COM -s
```

