# This file "Pro...pkt" is a saved file for Packet Tracer Program From Cisco
### adding a Device to the network as a host then giving it an ip different (Router IP) and Activating Telnet and SSH to control the Router Wirelessly(not for first time)

## How To Use?
- Open the packet Tracer Program.
- Click on the "File" tab then choose open.
- go to the saved file directory and vowala here we are.

## Steps:

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
            GigabitEthernet0/0     10.0.0.1        YES manual  administratively down down
            GigabitEthernet0/1     unassigned      YES unset   administratively down down 
            GigabitEthernet0/2     unassigned      YES unset   administratively down down 
            Vlan1                  unassigned      YES unset   administratively down down
          
            Zack(config-if)#no shutdown             -----> to activate this port
            Zack(config-if)#do sh int ip br
            Interface              IP-Address      OK? Method Status                 Protocol         
            GigabitEthernet0/0     10.0.0.1        YES manual  administratively up   down    -----> see now (up) mean activated but (down) in (protocol) mean that port is not plugged
            GigabitEthernet0/1     unassigned      YES unset   administratively down down 
            GigabitEthernet0/2     unassigned      YES unset   administratively down down 
            Vlan1                  unassigned      YES unset   administratively down down

            Zack(config-if)#exit            -----> to go to normal config mode
            Zack(config)#line vty 0 4       -----> users from 0 to 4 (5 users)
            Zack(config-line)#password zack -----> i gave all lines' access a password
            Zack(config-line)#login         -----> i activated these telnet lines

### now let's set up our pc:
- Connect the PC and Router with Straight cable which color is black in the G port in all of them.
- open pc by clicking on it and choose desktop tab then "IP address" is the first icon on the left.
- Click on it and gave it the IP (10.0.0.2) not (10.0.0.1) because it's reserved for the router.
- Change the subnet mask from default (255.0.0.0) to (255.255.255.0).
- Out from the X button up and choose now the Command Line or CMD.
- First type:

            C:\>ping 10.0.0.1               -----> we are testing if the router is working and connection is good.
            
            Pinging 10.0.0.1 with 32 bytes of data:

            Reply from 10.0.0.1: bytes=32 time=6ms TTL=255
            Reply from 10.0.0.1: bytes=32 time<1ms TTL=255
            Reply from 10.0.0.1: bytes=32 time<1ms TTL=255
            Reply from 10.0.0.1: bytes=32 time<1ms TTL=255

            Ping statistics for 10.0.0.1:
                Packets: Sent = 4, Received = 4, Lost = 0 (0% loss),
            Approximate round trip times in milli-seconds:
                Minimum = 0ms, Maximum = 6ms, Average = 1ms

            C:\>telnet 10.0.0.1             -----> we accessing router now wirelessly.
            Trying 10.0.0.1 ...Open


            User Access Verification
            Zack>exit           -----> very good it's working lest's out and give this access a password.

            [Connection to 10.0.0.1 closed by foreign host]

- From the CLI or the Terminal open the router and let's go:
            
            Zack(config)#line vty 0 4         
            Zack(config-line)#crypto key generate rsa         -----> i activated these lines.
            % Please define a domain-name first.
            Zack(config)#ip domain-name Zack
            Zack(config)#line vty 0 4
            Zack(config-line)#username Zack secret zack
            Zack(config-line)#login local                   -----> now we got our pass .        
- After we did it let's try again now

            C:\>telnet 10.0.0.1
            Trying 10.0.0.1 ...Open


            User Access Verification


            Username: Zack      -----> now write the username which was(Zack).
            Password:           -----> now write the password which was(zack).
            Zack>               -----> we will leave that for now.
### But actually telnet have a weak security SSH is better and more secure so let's try to activate it and delete the telnet connection:
- Open the Termianl and Router Settings with Config permission again and :

            Zack(config)#transpot input ssh         -----> no more telnet now.
            Zack(config)#line vty 0 4
            Zack(config-line)#crypto key generate rsa

            The name for the keys will be: Zack.Zack
            Choose the size of the key modulus in the range of 360 to 4096 for your
            General Purpose Keys. Choosing a key modulus greater than 512 may take
            a few minutes.

            How many bits in the modulus [512]: 1000        ----> the more you write the more encrypted password and connection will be but it will be slower.
            % Generating 1000 bit RSA keys, keys will be non-exportable...[OK]

            Zack(config)#line vty 0 4
            *Mar 1 0:12:52.279: %SSH-5-ENABLED: SSH 1.99 has been enabled           -----> our ssh is working now.
            Zack(config-line)#username Zack secret zack
            Zack(config)#line vty 0 4
            Zack(config-line)#ip ssh version 2              -----> let's make this connection out automatically after 1 minute.
            Zack(config)#line vty 0 4
            Zack(config-line)#exec-timeout 1
- Now let's open our cmd:

            C:\>telnet 10.0.0.1             -----> let's try to connect with telnet.
            Trying 10.0.0.1 ...Open

            [Connection to 10.0.0.1 closed by foreign host]    -----> not working anymore.

            C:\>ssh -l Zack 10.0.0.1                ------> let's try SSH by writing name(Zack) then IP(10.0.0.1).

            Password:                   -----> my password(zack).



            Zack>           -----> and it's working but let's wait for a minute without typing anything.
            Zack>exit       -----> automaticlly he get us out after 1 minute 

            [Connection to 10.0.0.1 closed by foreign host]


            [Connection to 10.0.0.1 closed by foreign host]
            C:\>                -----> so we done.