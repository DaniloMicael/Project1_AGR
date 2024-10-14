# Configuration File

## PC1
ip 10.1.1.70/26 10.1.1.65
```txt
    ip 100.100.100.1/24 100.100.100.2
    save
```

## PC2
```txt
    ip 191.1.1.72/28 191.1.1.71
    save
```

## PC3
```txt
    ip 192.168.1.73/24 192.168.1.1
    save
```

## PC4
```txt
    ip 191.1.1.4/27 191.1.1.5
    save
```

## PC5
```txt
    ip 192.168.0.5/24 192.168.0.55
    save
```

## PC6
```txt
    ip 191.1.1.56/28 ?????
    save
```

## PC7
```txt
    ip 192.168.2.7/24 ?????
    save
```

## PC8
```txt
    ip 192.168.3.8/24 192.168.3.5
    save
```

## PC9
```txt
    ip 192.168.3.9/24 192.168.3.5
    save
```

## PC10
```txt
    ip 192.168.6.10/24 192.168.6.1
    save
```

## PC11
```txt
    ip 192.168.6.11/24 192.168.6.2
    save
```

## PC12
```txt
    ip 191.1.1.42/28 191.1.1.34
    save
```

## PC13
```txt
    ip 192.168.5.43/24 192.168.5.2
    save
```

## PC14
```txt
    ip 192.168.4.14/24 192.168.4.1
    save
```

## PC15
```txt
    ip 192.168.4.15/24 192.168.4.2
    save
```

## Router 1
191.1.1.80/28
191.1.1.01010000/28

191.1.1.11110000/28
```txt
conf t
ip nat pool MYNATPOOL 191.1.1.82 191.1.1.83 191.1.1.84 191.1.1.85 netmask 255.255.255.240
access-list 2 permit 192.168.0.0 0.0.255.255
ip nat inside source list 2 pool MYNATPOOL

interface f0/0
ip nat inside
interface f0/1
ip nat inside
interface f1/0
ip nat inside
exit
interface f2/0
ip nat outside
```