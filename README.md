# CMD USED BY TB


## Device ID && cmd's

<!-- +99  for every device -->
1. `0x0001` -> RPI

2.   `0x0064` -> MSTR
3.   `0x0065` -> MSTR-SET-TIME
4.   `0x0066` -> MSTR-TIME-ACK
5.   `0x0067` -> MASTER-ACK-PDB
6.   `0x0068` -> PDB-ACK-COMPLETE
7.   `0x0069` -> INSERT-PDB
8.   `0x0070` -> EXTRACT-PDB
9. `0x00c8` -> SL1
10. `0x012c` -> SL2
11. `0x0190` -> SL3
12. `0x04b0` -> SL10

# Common cmd's 
<!-- from 10000  -->

10000. `0x2710` -> INIT

10001. `0x2711` -> INIT-COMPLETE
10002. `0x2712` -> PING
10003. `0x2713` -> PING-COMPLETE
10004. `0x2714` -> SET-TIME
10005. `0x2715` -> TIME-ACK
10006. `0x2416` -> LOG


# PDB TRIGGER STRUCTURE

### PDB INSERT CMD ORDER
```
                  1    2    3    4
[0x0064](0x0069){0xff,0xff,0xff,0xff}
```

|   1   |   2    |   3   |   4   |
| :---: | :----: | :---: | :---: |
|  INP  | S-BELT |  REV  |  AUX  |
| 0xff  |  0xff  | 0xff  | 0xff  |

### PDB EXTRACT CMD ORDER
```
                  1    2    3    7
[0x0001](0x0069){0xff,0xff,0xff,0xff}
```

|   1   |   2   |        3        |     4     |      5       |      6      |   7    |
| :---: | :---: | :-------------: | :-------: | :----------: | :---------: | :----: |
| break |  key  | can-bus-voltage | light-red | light-yellow | light-green | buzzer |
| 0xff  | 0xff  |      0xff       |   0xff    |     0xff     |    0xff     |  0xff  |
