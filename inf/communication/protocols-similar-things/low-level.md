# low-level

## NFC

NFC = Near field communication
NFC works via induction.
NFC works at a distance of up to ~4 cm

## PCI

PCI   Peripheral Component Interconnect
PCIe  Peripheral Component Interconnect Express
PCI is a parallel bus, PCIe is a serial bus
PCI, AGP (older), PCIe (today) are the protocols/connectors that were/are used to connect things on the motherbord, especially PC expansion cards but also some of the things soldered on.

## thunderbolt

Thunderbolt 1 and 2 are transmitted via the MiniDisplayPort connector.
Thunderbolt 3 and 4 are transmitted via the USB C connector.
Apple and Intel co-developed Thunderbolt around 2011.
Thunderbolt was designed to run over optic fiber cables, but actually generally runs over copper.
1|10 Gbit/s
2|20 Gbit/s
3|40 Gbit/s
4|40 Gbit/s

## DP

https://upload.wikimedia.org/wikipedia/commons/f/f1/DisplayPort_Connector.svg|DisplayPort Connector
flex-container:✫sm_300px-Mini_DisplayPort_on_Apple_MacBook.jpg✫|Mini DisplayPort Connector
Mini and nonmini ⟮DisplayPort⟯ is mainly for ⟮video / audio⟯, but can also carry ⟮USB⟯ and ⟮other data (e.g. thunderbolt)⟯

## ATA

ATA is short for Advanced Technology Attachment, though due to IBM trademarks its officially short for nothing.
ATA was renamed PATA after SATA was introduced.
ATA/PATA|parallel
SATA|serial
PATA ＆ SATA are interfaces for secondary storage
SATA is the successor to PATA
SATA
I|1.5Gb/s
II|3Gb/s
III|6Gb/s
III Rev 3.2|16 Gb/s

## usb

USB   Universal serial bus
USB can transmit both data of various kinds as well as power.
The speed of USB depends on the version of USB, indicated with a number.
The role in the master/slave architecture of USB is indicated by a letter.
The connector type of USB depends on the letter indicating its role within the master/slave system, as well as the size specifier.

A|Master
B|Slave
AB|complicated
C|Either Master or Slave dynamically

Size specifiers: ø, mini, micro.

USB C only exists as a single size.

USB versions: 1.0, 1.1, 2.0, 2.0 revised, 3.0, 3.1, 3.2, 4.0

Within USB 3, usb 3.1 and 3.2 were renamed

table:class=yesno;Standard |USB 1.0 |USB 1.1 |USB 2.0 |USB 2.0 Revised |USB 3.0 |USB 3.1 |USB 3.2 |USB4
type=th;Maximum transfer rate |span=2;12 Mbps |span=2;480 Mbps |5 Gbps |10 Gbps |20 Gbps |40 Gbps
type=th;Type A |span=4;<img src="https://upload.wikimedia.org/wikipedia/commons/7/7e/USB_Type-A_receptacle.svg" width="75" height="50"> |span=2;<img src="https://upload.wikimedia.org/wikipedia/commons/f/f4/USB_3.0_Type-A_receptacle_blue.svg" width="75" height="67"> |span=2;class=no;Deprecated
type=th;Type B |span=4;<img src="https://upload.wikimedia.org/wikipedia/commons/2/28/USB_Type-B_receptacle.svg" width="50" height="60"> |span=2;<img src="https://upload.wikimedia.org/wikipedia/commons/8/8c/USB_3.0_Type-B_receptacle_blue.svg" width="59" height="75"> |span=2;class=no;Deprecated
type=th;USB-C|span=3;class=no;N/A|span=5;<img src="https://upload.wikimedia.org/wikipedia/commons/0/07/USB_Type-C_Receptacle_Pinout.svg" height="80">
type=th;Mini-A|class=no;N/A|span=3;<img src="https://upload.wikimedia.org/wikipedia/commons/e/eb/USB_Mini-A_receptacle.svg" width="75" height="50"> |span=5;class=no;Deprecated
type=th;Mini-B|class=no;N/A|span=3;<img src="https://upload.wikimedia.org/wikipedia/commons/e/ec/USB_Mini-B_receptacle.svg" width="67" height="50"> |span=5;class=no;Deprecated
type=th;Mini-AB|span=3;class=no;N/A|<img src="https://upload.wikimedia.org/wikipedia/commons/f/f3/USB_Mini-AB_receptacle.svg" width="60" height="40"> |span=5;class=no;Deprecated
type=th;Micro-A|span=3;class=no;N/A|<img src="https://upload.wikimedia.org/wikipedia/commons/8/86/USB_Micro-A.svg" width="75" height="50"> |span=2;<img src="https://upload.wikimedia.org/wikipedia/commons/4/42/USB_3.0_Micro-A.svg" width="117" height="50"> |span=2;class=no;Deprecated
type=th;Micro-B|span=3;class=no;N/A|<img src="https://upload.wikimedia.org/wikipedia/commons/1/1b/USB_Micro-B_receptacle.svg" width="75" height="42"> |span=2;<img src="https://upload.wikimedia.org/wikipedia/commons/a/a8/USB_3.0_Micro-B_receptacle.svg" width="117" height="50"> |span=2;class=no;Deprecated
type=th;Micro-AB|span=3;class=no;N/A|<img src="https://upload.wikimedia.org/wikipedia/commons/6/6c/USB_Micro-AB_receptacle.svg" width="75" height="50"> |span=2;<img src="https://upload.wikimedia.org/wikipedia/commons/7/7a/USB_micro_AB_SuperSpeed.png/117px-USB_micro_AB_SuperSpeed.png" width="117" height="69"> |span=2;class=no;Deprecated

USB has a tree (bus + star) topology 


### usb 4

USB 4 was released in 2019.
As of USB 4, the only connector type is USB C.