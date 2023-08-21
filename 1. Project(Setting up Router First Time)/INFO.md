# This file "Pro...pkt" is a saved file for Packet Tracer Program From Cisco
### setting up CISCO router and changing it's hostname and password and it's port 0 ip and activate it.

## How To Use?
- Open the packet Tracer Program.
- Click on the "File" tab then choose open.
- go to the saved file directory and vowala here we are.

## Steps:
- Firstly to setup a Router we have to choose a Router, So let's Take Cisco 2911.
- Now we have to get a pc to show the terminal window on it.
- We get a Console Wire which is color "blue".
- Plug it in the "RS232" hub in the "PC or laptop" and the other side in the "Console" hub in the "Router".
- Click on "pc" and choose the "Desktop" tab and click on the "terminal" icon "Don't change anything just click OK".
- after "POST" is done you will get this message:
  
          Press RETURN to get started!
- JUST click "ENTER".
 
            Would you like to enter the initial configuration dialog? [yes/no]: 
- Type "n" or "no".
  
            Router>
- now this "Router" is called hostname which is default = "Router"  ,  and ">" is the user mode icon.
- first we have to change the host name and give it a password, but we can't do it in the user mode so we have to lvl up.
            
            Router>enable         "you can just write -en-".
            Router#               -----> now we are in admin mode but still not enough again so now config mode.
            Router#config
            Router(config)#       -----> now let's change the host name.
            Router(config)#hostname Zack
            Zack(config)#         -----> let's give it a password
            Zack(config)#enable password 1234         -----> but we have a problem it's very easy to guess or hack it look:
            Zack(config)#show run      -----> we have a problem this code can be used in admin mode we have a trick.
            Zack(config)#do show run    -----> before any cade if you are in mode higher than the command you can write "do" before the command.
            Building configuration...

            Current configuration : 710 bytes
            !
            version 15.1
            no service timestamps log datetime msec
            no service timestamps debug datetime msec
            no service password-encryption
            !
            hostname Zack
            !
            !
            !
            enable password 1234          -----> see we have to encrypt it
            !
            !
            !
            !
            !
            !
            ip cef
            no ipv6 cef
             --More--             -----> enter "space" to show more
          
            Zack(config)#enable secret zack
            Zack(config)#do sh run

            Building configuration...

            Current configuration : 757 bytes
            !
            version 15.1
            no service timestamps log datetime msec
            no service timestamps debug datetime msec
            no service password-encryption
            !
            hostname Zack
            !
            !
            !
            enable secret 5 $1$mERr$g.belFekn5IZA.bOprfkk0    -----> see now
            enable password 1234      -----> this not working now so we can we remove it
            !
            !
            !
            !
            !
            !
            ip cef
             --More--

            Zack(config)#no enable password

            Building configuration...

            Current configuration : 757 bytes
            !
            version 15.1
            no service timestamps log datetime msec
            no service timestamps debug datetime msec
            no service password-encryption
            !
            hostname Zack
            !
            !
            !
            enable secret 5 $1$mERr$g.belFekn5IZA.bOprfkk0
            !
            !
            !
            !
            !
            !
            ip cef
             --More--

            Zack(config)#do sh int ip br          -----> we will choose a port and give it ip and subnet mask.

            Interface              IP-Address      OK? Method Status                Protocol 
            GigabitEthernet0/0     unassigned      YES unset  administratively down down          -----> we will choose port g0/0
            GigabitEthernet0/1     unassigned      YES unset  administratively down down 
            GigabitEthernet0/2     unassigned      YES unset  administratively down down 
            Vlan1                  unassigned      YES unset  administratively down down

            Zack(config)#int g0/0
            Zack(config-if)#ip address 10.0.0.1 255.255.255.0
            Zack(config-if)#do sh int ip br

            Interface              IP-Address      OK? Method Status                 Protocol 
            GigabitEthernet0/0     10.0.0.2        YES manual  administratively down down
            GigabitEthernet0/1     unassigned      YES unset   administratively down down 
            GigabitEthernet0/2     unassigned      YES unset   administratively down down 
            Vlan1                  unassigned      YES unset   administratively down down
          
            Zack(config-if)#no shutdown             -----> to activate this port

            Interface              IP-Address      OK? Method Status                 Protocol         -----> this will not appear i just show it to see that's working 
            GigabitEthernet0/0     10.0.0.2        YES manual  administratively up   down

            Zack(config-if)#do copy run start       -----> to save all we did for all devices or
            Zack(config-if)#do write
- ![Console connection](https://github.com/Zack-River/Network/assets/111385589/04a51cd6-b3bb-48ba-bd18-8977ce748e93)
