# Protection circuits, etc

Application Handbooks:
- https://efficiencywins.nexperia.com/efficient-products/nexperia-design-engineers-guides.html


## TVS Diodes for RS485 protection:
- [SM712.TCT, Semtech]()
- [SM712-02HTG, Littlefuse]()     
- [CDSOT23-SM712, Bourns]()
- [SM712, SMC Diodes]()
- [SM712, MCC]() 


## Battery protection
- [Diodes Inc AP9101C](https://www.diodes.com/assets/Datasheets/AP9101C.pdf)
- protection IC for li-ion/lipo battery with a high-precision voltage detection circuit.
- 1 cell
UVLO:
- [TI TLV840-Q1](https://www.ti.com/lit/ds/symlink/tlv840-q1.pdf?HQS=dis-mous-null-mousermode-dsf-pf-null-wwe&ts=1665089299484&ref_url=https%253A%252F%252Fnz.mouser.com%252F)
- Supervisor Open Drain or Open Collector 1 Channel SOT-23-5

## TVS diodes for surge protection:
- [RClamp0512TQ, Semtech](https://semtech.my.salesforce.com/sfc/p/#E0000000JelG/a/2R000000UtDY/PnVj0b2DqYIKna5HnuYzpjpX4oyG8yipaHBmtQWQMM0)
  - **D+ D- Solution**, Vrwm: 5V, low capacitance: 5pF max, dynamic resistance: 0.075 ohm typ.
  - Applications: 10/100/1000 Ethernet, 2.5GbE, USB 2.0, Automotive, Industrial
- [TDS2211P](https://semtech.my.salesforce.com/sfc/p/#E0000000JelG/a/2R000000UnaM/s6P7OygkYrTrUAHeHNJqh70C0XTvk6XFExvlymAGtD8)
  - **Vbus Solution**, Vrwm=22V, protects one I/O or power line.
  - Applications: USB PD, USB Type-C, IoT devices, storage devices, notebook/tablet computers, load switch input protection
- [RClamp3371ZC]()
  - **High Speed TX+/TX-, RX+/RX-**, Vrwm: 3.3V, 
  - protects one high speed data line, low cap: 0.25pF max, dynamic resistance: 0.14 ohm typ.
  - Applications: USB 3.1, USB 3.0, HDMI 1.4/2.0, USB Type-C, Thunderbolt, 10GbE
- NB: TVS diodes can be paralleled to achieve higher current shunt ratings.
- [ESD Protection of USB Type-C Interfaces, Semtech](https://blog.semtech.com/esd-protection-of-usb-type-c-interfaces)

<img src="https://user-images.githubusercontent.com/42329930/208318536-1e4d6e79-09b3-47f0-a64e-13a74f21af3e.png" width="60%" height="60%">

## Ethernet transformer
- The primary purpose is isolation. Typically they are also used as part of the signal conditioning, turning a pair of single-ended drives into a differential signal on transmit and establishing the correct common mode voltage for the receiver on receive.
- [TC2500, from Pulse](https://productfinder.pulseelectronics.com/api/open/part-attachments/datasheet/tc2500p)
  - transformers for LAN Inter (1Gigabit, 2.5Gigabit, 5Gigabit, 10Gigabit) 
  - see TC2500P for PoE
  

## NIS3071 48V 4-Channel Integrated eFuse
- -0.5 to 60 V input voltage range
- 4 Independent integrated eFuses in one package
- 2.5A Continuous current operation for each channel
- 80 mΩ RDSon TYP @ 25 °C (1 A); each channel
- -40 to 150°C TJ operating range  
![image](https://user-images.githubusercontent.com/42329930/210479730-e261bee9-abc4-4757-8154-760811347c5a.png)


## Current regulation / management
TPS25221DBVT, Texas Intstruments
- IC CURRENT SWITCH 2A SOT23-6 (aka USB power switch)
- Intended for applications where heavy capacitive loads and short circuits may be encountered. 
- Programmable I_limit (set between 275mA and 2.7A using external resistor).
- When a load attempts to draw current exceeding I_limit the internal FET enters constant current mode to keep I_load at or below I_limit.
- https://www.ti.com/general/docs/suppproductinfo.tsp?distId=10&gotoUrl=https%3A%2F%2Fwww.ti.com%2Flit%2Fgpn%2Ftps25221


LS0505EVD22, Little Fuse
- Electronic Fuse Regulator 5A 10-DFN (2x2)
- https://www.littelfuse.com/media?resourcetype=datasheets&itemid=1bf74099-32be-4af5-b3e1-7da02015becb&filename=littelfuse-over-voltage-protection--ls0505evd22-datasheet-(1)

## IEC 61000-4-5 8/20 μs waveform
![image](https://user-images.githubusercontent.com/42329930/210915894-a2790126-6414-4078-bef0-43d1dc8a0c17.png)


## IEC61643-123 10/1000 μs waveform
![image](https://user-images.githubusercontent.com/42329930/210916462-840cd892-08be-4ed3-a677-ff83efa5d86e.png)

Basics of ESD Protection (TVS) Diodes (A Toshiba presentation):
- https://toshiba.semicon-storage.com/info/application_note_en_20220527_AKX00461.pdf?did=68869


## Surge Switch
![image](https://user-images.githubusercontent.com/42329930/210920093-6fe92410-097c-4658-8088-bcc23f16c95a.png)

VI comparison curve:
![image](https://user-images.githubusercontent.com/42329930/210920176-3866c822-f7ee-4405-aaef-d6a587069335.png)
