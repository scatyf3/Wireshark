arp: IP->MAC addr

![here is my understanding of this pcap](image.png)

here is the arp protocol

```ARP

Address Resolution Protocol (request)
    Hardware type: Ethernet (1)
    Protocol type: IPv4 (0x0800)
    Hardware size: 6
    Protocol size: 4
    Opcode: request (1)
    Sender MAC address: CnetTech_73:8d:ce (00:80:ad:73:8d:ce)
    Sender IP address: 192.168.1.104
    Target MAC address: 00:00:00_00:00:00 (00:00:00:00:00:00)
    Target IP address: 192.168.1.117

```
## 1

> What is the 48-bit Ethernet address of your computer?

AmbitMic_a9:3d:68 (00:d0:59:a9:3d:68)



> What is the 48-bit destination address in the Ethernet frame? Is this the Ethernetaddress of gaia.cs.umass.edu? (Hint: the answer is no). What device has this as its Ethernet address? [Note: this is an important question, and one that students sometimes get wrong. Re-read pages 468-469 in the text and make sure you understand the answer here.]

- destination address in the Ethernet frame is ff:ff:ff:ff:ff:ff
- Is this the Ethernetaddress of gaia.cs.umass.edu? NO
- device is switch
    - not sure, what is the broadcast device in real life???

```
Ethernet II, Src: AmbitMic_a9:3d:68 (00:d0:59:a9:3d:68), Dst: Broadcast (ff:ff:ff:ff:ff:ff)
    Destination: Broadcast (ff:ff:ff:ff:ff:ff)
    Source: AmbitMic_a9:3d:68 (00:d0:59:a9:3d:68)
    Type: ARP (0x0806)

```


> Give the hexadecimal value for the two-byte Frame type field. What upper layer protocol does this correspond to?

Protocol type: IPv4 (0x0800)


> How many bytes from the very start of the Ethernet frame does the ASCII “G” in “GET” appear in the Ethernet frame?

here is G appear in the Ethernet frame?

![Alt text](image-1.png)


## 2
here is the Ethernet frame contains the http respond message

```
Ethernet II, Src: LinksysG_da:af:73 (00:06:25:da:af:73), Dst: AmbitMic_a9:3d:68 (00:d0:59:a9:3d:68)
    Destination: AmbitMic_a9:3d:68 (00:d0:59:a9:3d:68)
        Address: AmbitMic_a9:3d:68 (00:d0:59:a9:3d:68)
        .... ..0. .... .... .... .... = LG bit: Globally unique address (factory default)
        .... ...0 .... .... .... .... = IG bit: Individual address (unicast)
    Source: LinksysG_da:af:73 (00:06:25:da:af:73)
        Address: LinksysG_da:af:73 (00:06:25:da:af:73)
        .... ..0. .... .... .... .... = LG bit: Globally unique address (factory default)
        .... ...0 .... .... .... .... = IG bit: Individual address (unicast)
    Type: IPv4 (0x0800)

```

>What is the value of the Ethernet source address? Is this the address of your computer, or of gaia.cs.umass.edu (Hint: the answer is no). What device has this as its Ethernet address?

Src:LinksysG_da:af:73 (00:06:25:da:af:73), it is the address of router

![if you google "linksysG", you can get the answer:)](image-2.png)

>What is the destination address in the Ethernet frame? Is this the Ethernet address of your computer?

Dst: AmbitMic_a9:3d:68 (00:d0:59:a9:3d:68), and is my computer

>Give the hexadecimal value for the two-byte Frame type field. What upper layer protocol does this correspond to?

Type: IPv4 (0x0800)

>How many bytes from the very start of the Ethernet frame does the ASCII “O” in “OK” (i.e., the HTTP response code) appear in the Ethernet frame?

here is OK:

![Alt text](image-3.png)

## 3:ARP caching

>Write down the contents of your computer’s ARP cache. What is the meaning of each column value?

here is my arp caching

```
➜  ~ arp -a
? (172.23.128.1) at fc:60:9b:aa:3e:1 on en0 ifscope [ethernet]
? (172.23.142.179) at b0:dc:ef:13:9f:93 on en0 ifscope [ethernet]
? (172.23.205.165) at 36:25:ff:15:f0:a5 on en0 ifscope [ethernet]
? (172.23.205.183) at cc:8:fa:65:60:2a on en0 ifscope permanent [ethernet]
? (172.23.241.229) at ac:50:de:74:a3:b7 on en0 ifscope [ethernet]
? (172.23.243.77) at b0:35:9f:a9:60:5f on en0 ifscope [ethernet]
mdns.mcast.net (224.0.0.251) at 1:0:5e:0:0:fb on en0 ifscope permanent [ethernet]
? (239.255.255.250) at 1:0:5e:7f:ff:fa on en0 ifscope permanent [ethernet]
```

- 172.23.xxx.xx