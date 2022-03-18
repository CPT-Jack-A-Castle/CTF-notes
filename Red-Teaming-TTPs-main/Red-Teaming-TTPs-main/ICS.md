# ICS/SCADA enumeration techniques for safe and effective scanning, network reconnaissance, and tactical host probing.

######################################################################

## General Enumeration:

```
nmap -Pn -sT --scan-delay 1s --max-parallelism 1 \
    -p
    80,102,443,502,530,593,789,1089-1091,1911,1962,2222,2404,4000,4840,4843,4911,9600,19999,20000,20547,34962-34964,34980,44818,46823,46824,55000-55003 \
    <target>
```

######################################################################

## Modbus Scanning

```
nmap -Pn -sT -p502 --script modbus-discover <target>

nmap -sT -Pn -p502 --script modbus-discover --script-args modbus-discover.aggressive=true <target>
```

######################################################################

## Bacnet

```
nmap -Pn -sU -p47808 --script bacnet-info <target>

# Siemens Bacnet P2 Enumeration 

nmap -Pn -sT -n -T4 -p5033 <target> 
```

######################################################################


## Enip

```nmap -Pn -sU -p44818 --script enip-info <target>```

######################################################################


## Niagara fOX

```nmap -Pn -sT -p1911,4911 --script fox-info <target>```

######################################################################


## Omron

```nmap -Pn -sU -p9600 --script omrom-info <target>```

## PCWorx Devices

PCWorx devices allow unaunthenticated requests that query for system information.

```nmap -Pn -sT -p1962 --script pcworx-info <target>```

# Shodan.io Queries

## PLCs

Siemens S7-1200 PLC

```
Location: /Default.mwsl
```

Omron CJ2 PLCs

```
Product name: CJ2*
```

Schneider Electric PLCs

```
Device Identification: Schneider Electric
```

## Maritime 

K4 Edge Routers and Maritime VSAT

```
"k4DCP5" country:US
```

KVH Commbox Terminals

```
html:commbox
```

Cobham Sailor 900

```
title:”sailor 900"
```

## Miscellaneous

TeamViewer

```
port:5938 "\x17$\x11\x04\x00"
```

Yealink T49G VOIP Phones

```
Yealink T49G
```

