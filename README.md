# NETWORK CCNA 200-301 & ENCORE 350-401 (JOURNEY, SUMMARY and DOCUMENTRY)

## NETWORKS TYPES:
### LAN:                 
                                                                                                            
  - Small network (area and space not as num of Devices).  
  - unlimited number of devices connected together.              
  - Devices can only talk with each other(on the same network only).               

### WAN:

  - Big network ------> (countries , Corporate branches).
  - unlimited number of devices connected together.
  - Devices can talk with anyone like the internet.
    
  ![2  LAN vs WAN](https://github.com/Zack-River/Network/assets/111385589/10c09024-e300-4ce4-8e7d-7aedf910cf0b)



## What do you need to Make a Network?

  - Host -----> PC - End Devices
  -  Router - switch
  -  Cables (UTP - Fiber Optic)

  ![3  Network example](https://github.com/Zack-River/Network/assets/111385589/6fd40956-78b8-44c8-8de5-658b118215eb)        


## Cable TYPES:
### 1-UTP WIRE

- (Pairs of wires one of them to send and other to receive).
- (more twisted means faster data transportation).
- (wires color order is const for every connection Method).                                               
- 1 silky wire to reduce noise and make it More flexible.
- Connector (RJ 45).
-  ![](https://github.com/Zack-River/Network/assets/111385589/1b2649dd-d796-47cc-aef9-81e9d54a7642)      
- works in range (1m to 100 meter).
- for pc-pc or pc-router pc-switch connection.
- cheap(price).  
- Toss(Coxial) -----> used for tv signals.
###  n base T ------> n refers to speed(mgb per sec)  , T refers to UTP 

#### 10 base T (cat 5)                      
#### 100 base T (cat 5e ----> enhanced)   
#### 1000 base T (cat 6)

                                                       
 


### Straight Connection(standard) for different devices except (pc - router):

- white orange
- orange
- white green
- blue
- white blue
- green
- white brown
- brown
- ![4-b  Straight connection](https://github.com/Zack-River/Network/assets/111385589/eac44548-4a24-4242-a3f8-fd509af56657)


### Cross Over connection for similar Devices (pc - pc , pc - router , router - router , etc.....):
#### 1 in straight is 3 in cross over and 2 in straight is 6 in cross over:

- white green
- green 
- white orange
- blue
- white blue
- orange
- white brown
- brown
- ![4-c  Crossover connection](https://github.com/Zack-River/Network/assets/111385589/4a8f05eb-d603-49ea-9843-10b6eb9fd665)



### Manual Console cable( Rollover ) used to setup IPs and settings for routers for the first time:
#### verse of the straight connection:

- brown
- white brown
- green
- white blue
- blue
- white green
- orange
- white orange                            
- ![4-d  Rollover connection](https://github.com/Zack-River/Network/assets/111385589/69bacdb1-008a-4930-b918-9dfc02842ef9)

### 2-Fiber Optic:

- Single mode( 9micron )
- Multi mode( 62micron )(better)
- ![5-a  Single Mode vs Multimode Fiber](https://github.com/Zack-River/Network/assets/111385589/3508ca54-bf4d-4190-802f-cedf6acbe2dc)
- Connectors ( LC - FC - SC - ST )
- ![5  Fiber optic cable and his connectors](https://github.com/Zack-River/Network/assets/111385589/1221f433-bca0-42cf-a976-6d746202834e)
      


##### n base f ------> n refers to speed(mgb per sec)  , f refers to fiber optic wire

#### "fiber optic patch cored wire" is a wire which has it's "connector" and ready to plug in

- very high speed.
- works in a bigger range (500m to 80km).
- not affected by distance.
- no colors just plug it.
- servers connection etc..    
- expensive.
 
- ![6  Networking cables Comparison](https://github.com/Zack-River/Network/assets/111385589/210821aa-609b-4575-959d-38d4cc744fb8)



## Some protocols and its use

- HTTP(80) / HTTPS(443) -----> Browsing.

- FTP(21) -----> Downloading.

- SMTP(25) -----> Send Emails.

- POP(110) ----->  Receive Emails.
                                                                 
- IP -----> Internet Protocol.



## Every Device Must Have :

- IP (built in the NIC(Network Interface Controller) *Can be Edited*).

- Protocols (To send and recieve).

- Port (Gate on OS which controls the Protocols **65536 Port**).



## Casting:

- UNICAST (One to One -----> Whatsapp , Facebook).

- MULTICAST (One to Many -----> Zoom , Meets , Whatsapp Groups).

- BROADCAST (One to All -----> not on internet , TV channels).


## IP Addressing (IPv4 *More used and common* - IPv6):

- IPv4 is 4 octet -----> x.x.x.x  where x is a num (0-255).

- Octet mean 8 binary num for each cell x -------> 192.168.100.1 = 11000000 . 10101000 . 01100100 . 00000001

- base of cells is ------->    128 - 64 - 32 - 16 - 8 - 4 - 2 - 1     BIN to DEC

      128  64  32  16  8   4   2   1                    128  64  32  16  8   4   2   1                          128  64  32  16  8   4   2   1                       128  64  32  16  8   4   2   1
                                      = 128 + 64 = 192                                   = 128 + 32 + 8 = 168                                   = 64 + 32 + 4 = 100                                   = 1    
       1   1   0   0   0   0   0   0  = 8bits            1    0   1  0   1   0   0   0   = 8bits                 0    1   1  0   0   1   0   0  = 8bits               0    0   0  0   0   0   0   1   = 8bits
                                                                                        
                                                                                  192.168.100.1    ----->   32 bits
                                                                                                        




## Subnet Mask:

### we can have 2 IPs the same but Subnet Mask is the important thing which controls how many devices in the same network and is they are in the same network or not.

### There are 2 Ways to make your subnet mask -----> First and Easiest one is to choose from the default classes Based On How many Devices on the network:

- Class C -----> 255.255.255.0 MAX 254 Device = on the network.
- Class B -----> 255.255.0.0  MAX = 65K Device on the Network.
- Class A -----> 255.0.0.0 MAX = 16M Device on the Network.

### Second Way and the better one is by Making a Custom Subnet to reduce the echo (if you choosed class b and you have 1000 Device there's empty 64000 Place which mean 64K echo Msg which reduce speed and consume more).


## How to make a custom Subnet Mask?

#### 1- Choose a Random ip which prefered to start with (192.168.x.x - 10.x.x.x - 172.16.x.x).

#### 2- then Select the number of devices (EX: 1000).

#### 3- now 2^h >= 1000  -----> so h = 10    2^10 = 1024 not 2^9 = 512 < 1000 and not 2^11 = 2048 >>> 1000

- h is the number of 0s on the right of the octet binary.

- n is the number of the 1s on the left of the octet Binary = 32bit - hbit = 32 - 10 = 22.

        Subnet Mask:  1    1   1   1   1   1   1   1.   1   1   1   1   1   1   1   1.   1   1   1   1   1   1   0   0.   0   0   0   0   0   0   0   0  :Subnet Mask
        Counter (n):  1    2   3   4   5   6   7   8    9   10  11  12  13  14  15  16   17  18  19  20  21  22  10  9    8   7   6   5   4   3   2   1  :(h) Counter
        subnet: 11111111.11111111.11111100.00000000 -------> 255.255.252.0

      -we will choose 192.168.54.3 as the random ip and we will now calc the (subnet ip - first valid ip - last valid ip - broadcast).
- 192.168.54.3 -----> 11000000.10101000.00110110.00000011

#### (only 1 + 1 = 1 , other = 0)
    1   1   1   1   1   1   1   1   1   1   1   1   1   1   1   1   1   1   1   1   1   1   0   0   0   0   0   0   0   0   0   0
    +                                                                                                                               
    1   1   0   0   0   0   0   0   1   0   1   0   1   0   0   0   0   0   1   1   0   1   1   0   0   0   0   0   0   0   1   1
    -----------------------------------------------------------------------------------------------------------------------------
    1   1   0   0   0   0   0   0   1   0   1   0   1   0   0   0   0   0   1   1   0   1   0   0   0   0   0   0   0   0   0   0
    11000000.10101000.00110100.00000000 -----> 192.168.52.0 / 255.255.252.0 = 192.168.52.0 / 22 -----> (22) is n (num of 1s in the subnet mask) (CIDR *ClassLess InterDomain Routing*).
                                

                                    -subnet ip = 192.168.52.0               -first valid ip = subnet + 1 = 192.168.52.1

### To get the broadcast ip turn h ( num of first zeros on the right in the subnet mask ) in subnet ip to 1s.

#### subnet (192.168.52.0)11000000.10101000.001101(00.00000000) -----> 11000000.10101000.001101(11.11111111) = 192.168.55.255
                    
- subnet ip = 192.168.52.0

- first valid ip = subnet + 1 = 192.168.52.1

- last valid ip = broadcast ip - 1 = 192.168.55.254

- Broadcast ip = 192.168.55.255


### But what after as example 5 years you needed to add more 1000 device. do you need to repeat all of this again?
#### ofcourse not, you just have to know the BlockSize (pattern between the old subnet and new one).

#### how to get the new subnet just add 1 to the broadcast ---------- 192.168.55.255 + 1 = 192.168.56.0(new subnet ip).
                    
### Now:
                    Old:                BlockSize is +4 in the 3rd octet           New:
    subnet ip = 192.168.(52).0                          --> (52+4) --> -subnet ip = 192.168.(56).0
    first valid ip = subnet + 1 = 192.168.(52).1        --> (52+4) --> -first valid ip = 192.168.(56).1
    last valid ip = broadcast ip - 1 = 192.168.(55).254 --> (55+4) --> -last valid ip = 192.168.(59).254
    Broadcast ip = 192.168.(55).255                     --> (55+4) --> -Broadcast ip = 192.168.(59).255


### actually if we used the default way to know if 2 devices on the same network it will take a long time so there's better way to do it:
      - 10.20.30.40 / 19 as example this ip we have to specify the subnet of it:
      19 means -----> 8bits + 8bits + 3bits -----> octet number 3 
      BlockSize = 3 (128 64 (32) 16 8 4 2 1) = 32  so we will start from octet 3 = 0 and then add +32 each sub

      sub1 10.20.0.0              so our ip  = 10.20.30.40  which means it's on sub 1
      sub2 10.20.32.0             
      sub3 10.20.64.0
      sub4 10.20.96.0             etc.......
------------------------------


### Example.2:
      - 10.15.25.35 / 21 ----->       8 + 8 + 5   OCTET 3   (128 64 32 16 (8) 4 2 1)   BlockSize = 8
      sub1 10.15.0.0
      sub2 10.15.8.0             
      sub3 10.15.16.0
      sub4 10.15.24.0             so our ip  = 10.15.25.35  which means it's on sub 4
      sub4 10.15.32.0
------------------------------



### Problem.1 :    is these 2 Devices on the same Subnet?
      - 10.70.70.7 / 10 ----->       8 + 2   OCTET 2   (128 (64) 32 16 8 4 2 1)   BlockSize = 64
      sub1 10.0.0.0
      sub2 10.64.0.0              so our ip  = 10.70.70.7  which means it's on sub 2            
      sub3 10.128.16.0

      - 10.100.100.100 / 10 ----->   8 + 2   OCTET 2   (128 (64) 32 16 8 4 2 1)   BlockSize = 64
      sub1 10.0.0.0
      sub2 10.64.0.0              so our ip  = 10.100.100.100 which means it's on sub 2 
      sub3 10.128.0.0

- so Device(1) and Device(2) are on the same sub and network
------------------------------


### Problem.2:      is these 2 Devices on the same Subnet?
      - 10.10.10.10 / 21 ----->      8 + 8 + 5  OCTET 3 (128 64 32 16 (8) 4 2 1) BlockSize = 8
      sub1 10.10.0.0
      sub2 10.10.8.0              so our ip  = 10.10.10.10 which means it's on sub 2 
      sub3 10.10.16.0

      - 10.10.17.10 / 21 ----->      8 + 8 + 5  OCTET 3 (128 64 32 16 (8) 4 2 1) BlockSize = 8
      sub1 10.10.0.0
      sub2 10.10.8.0
      sub3 10.10.16.0              so our ip  = 10.10.17.10 which means it's on sub 3 

- so Device(1) and Device(2) aren't on the same sub or network
------------------------------


## IP Default Classes
### Known from its first Octet:
      * Class Name *     * First IP *        * Last IP *        * Default Subnet Mask *
        Class A   From     1.0.0.0    To    126.255.255.255        Class C 255.0.0.0
        Class B   From    128.0.0.0   To    191.255.255.255       Class B 255.255.0.0
        Class C   From    192.0.0.0   To    223.255.255.255      Class A 255.255.255.0   
        Class D   From    224.0.0.0   To    239.255.255.255    Reserved For Multi Casting 
        Class E   From    240.0.0.0   To    254.255.255.255    Expermential Made as backup

- Class A IPs 127.0.0.0   To 127.255.255.255  Can't Be used and is reserved for loopback Testing.
- D , E Classes can't be used Too.
- 127.0.0.1     Reserved For local Hosting.

### MultiCasting IPs Searches for each other To Link like ZOOM.

#### There are only 2 important TTLs.
- TTL 64 Means that this site or ip works on Linux OS.
- TTL 128 Means that this site or ip works on Windows Server OS.


## Cisco Devices and How to connect for the First Time:

### Common Parts:
- CPU ----> Processing Data and IPs(0s , 1s).
- RAM ----> System Runs on.
- FLASH ----> Like HDD where exist Source.bin file and Config.bin file.
- NVRAM ----> Like HDD but for saving your configs.


#### Switch has no Turn ON/OFF button.
#### Router has Turn ON/OFF button.


#### To setup Cisco Router or any router which has OS you have to Get a Roll Over Wire and Plug it in the Console port 
- ![819_console_port](https://github.com/Zack-River/Network/assets/111385589/71635d83-8f3e-403c-8162-415c736c8c02)      ![Console-Cable2](https://github.com/Zack-River/Network/assets/111385589/29629c1f-fa0f-477d-85d9-177cf7252395)




- after you plug it in now use the putty app to show the router terminal screen which will show first the POST then you can no Configure it.
- Other way is same steps but virtually with packet tracer from Cisco Website.
 
 ### Now You can go to the Projects Folder to see the steps and my Work(Project 1 and 2).


##  TCP vs UDP and OSI TCP Models(Layers):
### 1- TCP(Transmission Control Protocol):
- Connection Oriented "Reliable".
- 3 Ways handshake.
- Test connection First Then Send and Receive. 
- Sequence(Every Packet has a num) if amount if send of receive packets = send packets then Connection done correctly.
- CheckSum (he turns the data into bits packets then put it into frames to make it easier to transport).
- Testing:
- 

### 2- UDP(User Datgram Protocol):
- No testing.
- Faster.
- Continuous (no stop) lost data can't be restored (Like streams - calls - ZOOM meetings - etc.....).

## What's Layers and Models?
### Describing for data transformation from 0s and 1s To Understandable information:
#### OSI (Open System Interconnection) (7 STAGES) vs TCP (4 STAGES):
- ARP(Address Resolution Protocol) is the protocol in switches(ex) which reads the mac addresses.
- in physical layer -----> bits turns to decimals or hexa decimals.
- layers from (5 : 7) is upper layers and other is lower.
- layer with higher num is more intelligent and complicated.

