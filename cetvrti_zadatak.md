4._Proveriti dostupnost Web servera na adresi www.fon.bg.ac.rs korišćenjem programa ping. Koje
je srednje vreme odziva? Na kom čvoru paketi izlaze iz lokalne mreže, kako se zove taj čvor? Da li
neki čvor filtrira ping pakete?

```sh
Z:\home\stefan24>ping www.fon.bg.ac.rs
Pinging www.fon.bg.ac.rs [147.91.134.111] with 32 bytes of data:
Reply from 147.91.134.111: bytes=32 time=203ms TTL=45
Reply from 147.91.134.111: bytes=32 time=123ms TTL=45
Reply from 147.91.134.111: bytes=32 time=124ms TTL=45
Reply from 147.91.134.111: bytes=32 time=125ms TTL=45

Ping statistics for 147.91.134.111
        Packets: Sent = 4, Received = 4, Lost = 0 (0% loss)
Approximate round trip times in milli-seconds:
        Minimum = 123ms, Maximum = 203ms, Average = 144ms
        
```

**SREDNJE VREME ODAZIVA JE  'Average = 144ms'**

```sh
traceroute www.fon.bg.ac.rs
traceroute to www.fon.bg.ac.rs (147.91.134.111), 30 hops max, 60 byte packets
 1  _gateway (10.38.200.25)  2.591 ms  3.442 ms  4.274 ms
 2  * * *
 3  10.150.21.1 (10.150.21.1)  203.728 ms  203.699 ms  203.672 ms
 4  10.253.134.189 (10.253.134.189)  203.645 ms  203.848 ms  203.772 ms
 5  * * *
 6  77.243.16.161 (77.243.16.161)  204.230 ms  452.275 ms  273.157 ms
 7  * * *
 8  lag14-9079.as8447.a1.net (195.3.64.202)  273.091 ms  273.079 ms  273.067 ms
 9  lag6-9070.as8447.a1.net (195.3.64.230)  273.229 ms  273.213 ms  273.025 ms
10  lag1-9083.as8447.a1.net (195.3.64.190)  273.190 ms  273.004 ms  274.278 ms
11  nl-ams.nordu.net (80.249.209.203)  274.305 ms  274.293 ms  274.819 ms
12  213.46.175.38 (213.46.175.38)  117.748 ms  117.723 ms  117.708 ms
13  * * *
14  amres-ias-geant-gw.zag.hr.geant.net (83.97.89.28)  117.798 ms  117.583 ms  117.561 ms
15  amres-ias-geant.zag.hr.geant.net (83.97.89.29)  117.713 ms  116.735 ms  116.722 ms
16  147.91.5.192 (147.91.5.192)  117.124 ms  204.669 ms  204.639 ms
17  * * *
18  stanica-134-241.fon.bg.ac.rs (147.91.134.241)  204.748 ms  205.604 ms  204.708 ms
19  stanica-134-250.fon.bg.ac.rs (147.91.134.250)  203.771 ms  203.558 ms  199.718 ms
20  stanica-134-250.fon.bg.ac.rs (147.91.134.250)  199.687 ms  199.665 ms  199.606 ms
21  stanica-134-250.fon.bg.ac.rs (147.91.134.250)  199.552 ms  200.054 ms  198.632 ms
```
- **Paketi izlaze iz lokalne mreze na cvoru 1  _gateway (10.38.200.25).**
**Na putanji postoje čvorovi koji ne odgovaraju na ICMP zahteve, što ukazuje na filtriranje ping paketa, ali bez uticaja na komunikaciju sa krajnjim serverom.**