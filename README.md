# CMD USED BY TB


# Device ID

<!-- +99  for every device -->
1. `0x0001` -> RPI

---
100.   `0x0064` -> MSTR

101.   `0x0065` -> MSTR-SET-TIME
102.   `0x0066` -> MSTR-TIME-ACK
103.   `0x0067` -> MASTER-ACK-PDB
104.   `0x0068` -> PDB-ACK-COMPLETE
105.   `0x0069` -> INSERT-PDB
106.   `0x0070` -> EXTRACT-PDB


---
200. `0x00c8` -> SL1
---
300. `0x012c` -> SL2
---
400. `0x0190` -> SL3
---
1000. `0x04b0` -> SL10

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

```
                  1    2    3    4
[0x0064](0x0069){0xff,0xff,0xff,0xff}
```
### PDB INSERT CMD ORDER

| 1    | 2      | 3    | 4    |
| ---- | ------ | ---- | ---- |
| INP  | S-BELT | REV  | AUX  |
| 0xff | 0xff   | 0xff | 0xff |

```
                  1    2    3    7
[0x0001](0x0069){0xff,0xff,0xff,0xff}
```
### PDB EXTRACT CMD ORDER

| 1     | 2    | 3               | 4         | 5            | 6           | 7      |
| ----- | ---- | --------------- | --------- | ------------ | ----------- | ------ |
| break | key  | can-bus-voltage | light-red | light-yellow | light-green | buzzer |
| 0xff  | 0xff | 0xff            | 0xff      | 0xff         | 0xff        | 0xff   |
