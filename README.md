# NETWORK CCNA 200-301 & ENCORE 350-401 JOURNEY and SUMMARY


                                               //-------------------------- NETWORKS TYPES --------------------------//

                                  <<<< LAN >>>>                                     |                                   <<<< WAN >>>>                 
                                                                                    |                                                         
1-              Small network (area and space not as num of Devices)                |            Big network ------> (countries , Corporate branches)    
2-                  unlimited number of devices connected together                  |               unlimited number of devices connected together                 
3-           Devices can only talk with each other(on the same network only)        |               Devices can talk with anyone like the internet                 




                                        //-------------------------- What do you need to Make a Network? --------------------------//

                                            1- Host -----> PC - End Devices   2- Router - switch     3- Cables (UTP - Fiber Optic)



                                                     //-------------------------- Cable TYPES --------------------------//

                                    1- UTP cables (Unshielded Twisted-Pair)                                        2- Fiber Optic Cables(Light Speed)
                             



                                                       //-------------------------- UTP WIRE --------------------------//
-(Pairs of wires one of them to send and other to receive).         -(more twisted means faster data transportation).       -(wires color order is const for every connection Method).
                                                        
                                        - 1 silky wire to reduce noise and make it More flexible.               -Connector (RJ 45).

                                 -works in range (1m to 100 meter).        -for pc-pc or pc-router pc-switch connection.           -cheap(price).  

                        - Toss(Coxial) -----> used for tv signals          - 10 base T (cat 5)        - 100 base T (cat 5e ----> enhanced)     -1000 base T (cat 6)

                                                        -n base T ------> n refers to speed(mgb per sec)  , T refers to UTP


                                            # Straight Connection(standard) for different devices except (pc - router):
                        1- white orange    2- orange     3- white green     4- blue     5- white blue     6- green    7- white brown     8- brown


                                            # Cross Over connection for similar Devices (pc - pc , pc - router , router - router , etc.....):
                                                    - 1 in straight is 3 in cross over and 2 in straight is 6 in cross over:
                        1- white green    2- green     3- white orange     4- blue     5- white blue     6- orange    7- white brown     8- brown



                                            # Manual Console cable( Rollover ) used to setup IPs and settings for routers for the first time:
                                                                     -verse of the straight connection:
                        1- brown    2- white brown     3- green     4- white blue     5- blue     6- white green    7- orange     8- white orange                            

# Fiber Optic:

                                                        -Single mode( 9micron )           -Multi mode( 62micron )(better)

                                                                       -Connectors ( LC - FC - SC - ST )

                                                -n base f ------> n refers to speed(mgb per sec)  , f refers to fiber optic wire

                                           -"fiber optic patch cored wire" is a wire which has it's "connector" and ready to plug in

            -very high speed.      -works in a bigger range (500m to 80km).  -not affected by distance.  -no colors just plug it.  -servers connection etc..    -expensive.


 //---- Some protocols and its use ----//

1- HTTP(80) / HTTPS(443) -----> Browsing.

2- FTP(21) -----> Downloading.

3- SMTP(25) -----> Send Emails.

4- POP(110) ----->  Receive Emails.
                                                                 
5- IP -----> Internet Protocol.



# Every Device Must Have :

1- IP (built in the NIC(Network Interface Controller) *Can be Edited*).

2-Protocols (To send and recieve).

3-Port (Gate on OS which controls the Protocols *65536 Port*).



//---- Casting ----//

1- UNICAST (One to One -----> Whatsapp , Facebook).

2- MULTICAST (One to Many -----> Zoom , Meets , Whatsapp Groups).

3- BROADCAST (One to All -----> not on internet , TV channels).


//---- IP Addressing (IPv4 *More used and common* - IPv6) ----//

-IPv4 is 4 octet -----> x.x.x.x  where x is a num (0-255).

-Octet mean 8 binary num for each cell x -------> 192.168.100.1 = 11000000 . 10101000 . 01100100 . 00000001

-base of cells is ------->    128 - 64 - 32 - 16 - 8 - 4 - 2 - 1     BIN to DEC

128  64  32  16  8   4   2   1
                                = 128 + 64 = 192
 1   1   0   0   0   0   0   0  = 8bits

128  64  32  16  8   4   2   1             
                                  = 128 + 32 + 8 = 168                
 1    0   1  0   1   0   0   0    = 8bits

128  64  32  16  8   4   2   1
                                = 64 + 32 + 4 = 100
 0    1   1  0   0   1   0   0  = 8bits

 128  64  32  16  8   4   2   1
                                 = 1
 0    0   0  0   0   0   0   1   = 8bits

192.168.100.1    ----->   32 bits




//---- Subnet Mask ----//

-we can have 2 IPs the same but Subnet Mask is the important thing which controls how many devices in the same network and is they are in the same network or not.

-There are 2 Ways to make your subnet mask -----> First and Easiest one is to choose from the default classes Based On How many Devices on the network:

Class C -----> 255.255.255.0 MAX 254 Device = on the network.
Class B -----> 255.255.0.0  MAX = 65K Device on the Network.
Class A -----> 255.0.0.0 MAX = 16M Device on the Network.

-Second Way and the better one is by Making a Custom Subnet to reduce the echo (if you choosed class b and you have 1000 Device there's empty 64000 Place which mean 64K echo Msg which reduce speed and consume more).


//---- How to make a custom Subnet Mask? ----//

-Choose a Random ip which prefered to start with (192.168.x.x - 10.x.x.x - 172.16.x.x).

-then Select the number of devices (EX: 1000).

-now 2^h >= 1000  -----> so h = 10    2^10 = 1024 not 2^9 = 512 < 1000 and not 2^11 = 2048 >>> 1000

-h is the number of 0s on the right of the octet binary.

-n is the number of the 1s on the left of the octet Binary = 32bit - hbit = 32 - 10 = 22.

Subnet Mask:  1    1   1   1   1   1   1   1.   1   1   1   1   1   1   1   1.   1   1   1   1   1   1   0   0.   0   0   0   0   0   0   0   0  :Subnet Mask
Counter (n):  1    2   3   4   5   6   7   8    9   10  11  12  13  14  15  16   17  18  19  20  21  22  10  9    8   7   6   5   4   3   2   1  :(h) Counter
subnet: 11111111.11111111.11111100.00000000 -------> 255.255.252.0

-we will choose 192.168.54.3 as the random ip and we will now calc the (subnet ip - first valid ip - last valid ip - broadcast).
192.168.54.3 -----> 11000000.10101000.00110110.00000011

        *(only 1 + 1 = 1 , other = 0)
 1   1   1   1   1   1   1   1   1   1   1   1   1   1   1   1   1   1   1   1   1   1   0   0   0   0   0   0   0   0   0   0
+                                                                                                                               
 1   1   0   0   0   0   0   0   1   0   1   0   1   0   0   0   0   0   1   1   0   1   1   0   0   0   0   0   0   0   1   1
 -----------------------------------------------------------------------------------------------------------------------------
 1   1   0   0   0   0   0   0   1   0   1   0   1   0   0   0   0   0   1   1   0   1   0   0   0   0   0   0   0   0   0   0
 11000000.10101000.00110100.00000000 -----> 192.168.52.0 / 255.255.252.0 = 192.168.52.0 / 22
 * (22) is n (num of 1s in the subnet mask) (CIDR *ClassLess InterDomain Routing*).
                                

-subnet ip = 192.168.52.0
-first valid ip = subnet + 1 = 192.168.52.1

#To get the broadcast ip turn h ( num of first zeros on the right in the subnet mask ) in subnet ip to 1s.

subnet (192.168.52.0)11000000.10101000.001101(00.00000000) -----> 11000000.10101000.001101(11.11111111) = 192.168.55.255
                    
-subnet ip = 192.168.52.0

-first valid ip = subnet + 1 = 192.168.52.1

-last valid ip = broadcast ip - 1 = 192.168.55.254

-Broadcast ip = 192.168.55.255


#But what after as example 5 years you needed to add more 1000 device. do you need to repeat all of this again?
-ofcourse not, you just have to know the BlockSize (pattern between the old subnet and new one).

#how to get the new subnet just add 1 to the broadcast        192.168.55.255 + 1 = 192.168.56.0(new subnet ip).
                    
Now:
                Old:                BlockSize is +4 in the 3rd octet           New:                                               
-subnet ip = 192.168.(52).0                          --> (52+4) --> -subnet ip = 192.168.(56).0
-first valid ip = subnet + 1 = 192.168.(52).1        --> (52+4) --> -first valid ip = 192.168.(56).1        
-last valid ip = broadcast ip - 1 = 192.168.(55).254 --> (55+4) --> -last valid ip = 192.168.(59).254
-Broadcast ip = 192.168.(55).255                     --> (55+4) --> -Broadcast ip = 192.168.(59).255           


#actually if we used the default way to know if 2 devices on the same network it will take a long time so there's better way to do it:
- 10.20.30.40 / 19 as example this ip we have to specify the subnet of it:
19 means -----> 8bits + 8bits + 3bits -----> octet number 3 and BlockSize = 3 (128 64 (32) 16 8 4 2 1) = 32  so we will start from octet 3 = 0 and then add +32 each sub

sub1 10.20.0.0              so our ip  = 10.20.30.40  which means it's on sub 1
sub2 10.20.32.0             
sub3 10.20.64.0
sub4 10.20.96.0             etc.......
------------------------------


Example.2:
- 10.15.25.35 / 21 ----->       8 + 8 + 5   OCTET 3   (128 64 32 16 (8) 4 2 1)   BlockSize = 8
sub1 10.15.0.0
sub2 10.15.8.0             
sub3 10.15.16.0
sub4 10.15.24.0             so our ip  = 10.15.25.35  which means it's on sub 4
sub4 10.15.32.0
------------------------------



Problem.1 :    is these 2 Devices on the same Subnet?
1- 10.70.70.7 / 10 ----->       8 + 2   OCTET 2   (128 (64) 32 16 8 4 2 1)   BlockSize = 64
sub1 10.0.0.0
sub2 10.64.0.0              so our ip  = 10.70.70.7  which means it's on sub 2            
sub3 10.128.16.0

2- 10.100.100.100 / 10 ----->   8 + 2   OCTET 2   (128 (64) 32 16 8 4 2 1)   BlockSize = 64
sub1 10.0.0.0
sub2 10.64.0.0              so our ip  = 10.100.100.100 which means it's on sub 2 
sub3 10.128.0.0

so Device(1) and Device(2) are on the same sub and network
------------------------------


Problem.2:      is these 2 Devices on the same Subnet?
1- 10.10.10.10 / 21 ----->      8 + 8 + 5  OCTET 3 (128 64 32 16 (8) 4 2 1) BlockSize = 8
sub1 10.10.0.0
sub2 10.10.8.0              so our ip  = 10.10.10.10 which means it's on sub 2 
sub3 10.10.16.0

2- 10.10.17.10 / 21 ----->      8 + 8 + 5  OCTET 3 (128 64 32 16 (8) 4 2 1) BlockSize = 8
sub1 10.10.0.0
sub2 10.10.8.0
sub3 10.10.16.0              so our ip  = 10.10.17.10 which means it's on sub 3 

so Device(1) and Device(2) aren't on the same sub or network
------------------------------
