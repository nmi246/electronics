# BLE Layers and what they are for/do:


![image](https://user-images.githubusercontent.com/42329930/225172132-58009dc9-4f2a-413e-bf77-3c70baf3397f.png)



## LE PHY: 
- physical layer
- use GFSK
- 40 RF channels with 2 GHz spacing
- operates in 2.4GHz ISM band
- ![image](https://user-images.githubusercontent.com/42329930/225172644-c7568182-0afc-4472-91ff-f1e8d1f28e8d.png)


## Link Layer: 
- 3 Advertising channels and 37 Data channel
- ![image](https://user-images.githubusercontent.com/42329930/225172752-fe2424c6-e5e6-48e4-83c9-cbcb29028e92.png)
- Advertisng channel: broadcast data for applications, contain advertising packets
  - beacones, sensors,
  - for discovering devices
  - advertising packets: device name + data ??
  - Extended advertising: ?? used to be 55 packets now it's 20-55 packets??
- 

![image](https://user-images.githubusercontent.com/42329930/225173358-b5cbfd10-880e-454b-aad1-ba7939cb094e.png)

Link layer (LL) state machine: 
![image](https://user-images.githubusercontent.com/42329930/225173829-a34ec3b8-89b9-42a4-99d8-6461f7d62b01.png)


## L2CAP
- logical link control and adaptation protocol
- provides logical channels
- multiplexed over one or more logical channels.

## SMP
- Security manager
  - how to pair, exchange keyes, encryption, decryption 
- SMP protocol codes:
  - ![image](https://user-images.githubusercontent.com/42329930/225174610-d7d9b310-7f94-4e5a-8237-935095cfa636.png)
- SMP pairing model:
  - ![image](https://user-images.githubusercontent.com/42329930/225174670-1c78e9ac-3619-401d-9d2d-578dda4c79db.png)
- SMP IO capabilites to algorithm
  - ![image](https://user-images.githubusercontent.com/42329930/225175000-ad31e266-7d18-41d3-966d-afa1a617c3a1.png)
 

## ATT
- Attribute protocol: used to determine how data is represented and exchanged between Server and client
- client vs server architecture
- how data is exchanged: server has data, client wants the data
  - ![image](https://user-images.githubusercontent.com/42329930/225175290-cb907808-4d49-4088-bec4-e6f93aa12fa7.png)
  - ![image](https://user-images.githubusercontent.com/42329930/225175346-655b428c-d005-4ccc-ab92-c377a19056ca.png)


## GATT (Generic attribute profile):
- defines concepts of:
  - service group
  - characteristic group
  - declarations
  - descriptors



## GAP (Genertic Access profile):
- used to make your device visible to outside world
- Profile roles:
  - Broadcaster, observer
  - peipheral, central  
- Defines std ways to devices to connect
  - discoverable, connectable, bonding    
- how to send data:
  - uses advertising packets

![image](https://user-images.githubusercontent.com/42329930/225177747-8fc16e83-0808-4eaf-af23-a928ea44d5df.png)
![image](https://user-images.githubusercontent.com/42329930/225177805-05d3dd41-c195-45d1-b791-913ff4c00882.png)
![image](https://user-images.githubusercontent.com/42329930/225178217-18714d0e-ded8-4405-9965-918a83a5d358.png)
??
Beacons = non connectible??


## Application layer:
- can make various designs using BLE services
- compatibility can be improved by using the BLE standard.







use this to shrink images to correct size:
<img src="https://user-images.githubusercontent.com/42329930/219544055-1ae474f8-1950-4d32-8dec-5c100b24f336.png" width="300">
