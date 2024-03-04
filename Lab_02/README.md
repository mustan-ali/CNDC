### **Cisco IOS Modes of Operation**  
   1. `Hostname>`  - User EXEC Mode (`enable` to enter Privileged EXEC Mode)
   2. `Hostname#`  - Privileged EXEC Mode (`configure terminal` to enter Global Configuration Mode)
   3. `Hostname(config)#`  - Global Configuration Mode

<br>

### **Setting up a Clock** 
   1. `Hostname> enable`  
   2. `Hostname# clock set 15:30:00 24 February 2024`  
   3. `Hostname# show clock`  

<br>

### **Basic Configuration of a Switch**
   1. `Switch> enable`  - Enter Privileged EXEC Mode  
   2. `Switch#  show running-config`  - Show the current configuration
   3. `Switch# configure terminal`  - Enter Global Configuration Mode
   4. `Switch(config)# hostname S1`  - Set the hostname to S1
   5. `S1(config)# line console 0`  - Enter Console Line Configuration Mode
   6. `S1(config-line)# password letmein`  - Set the console password
   7. `S1(config-line)# login`  - Enable login on the console
   8. `S1(config-line)# exit`  
   9. `S1(config)# enable password c1$c0`  - Set the privileged exec password(plaintext)
   10. `S1(config)# enable secret itsasecret`  - Set the privileged exec password(encrypted), overrides the enable password
   11. `S1(config)# service password-encryption`   - Encrypt all passwords(plaintext to encrypted)
   12. `S1(config)# banner motd "Authorized Access Only!"`  - Set the message of the day banner
   13. `S1(config)# exit`
   14. `S1# copy running-config startup-config`  - Save the configuration to NVRAM(Non-Volatile RAM)

<br>

### **Assigning IP Address to a Switch**
   1. `S1> enable`  
   2. `S1# configure terminal`
   3. `S1(config)# interface vlan 1`  - Enter Interface Configuration Mode
   4. `S1(config-if)# ip address 192.168.1.253 255.255.255.0`
   5. `S1(config-if)# no shutdown`  - Enable the interface

<br>

### **Setting up Virtual Terminal Lines(VTY)**
   1. `S1> enable`  
   2. `S1# configure terminal`
   3. `S1(config)# line vty 0 4`  - Enter VTY Line Configuration Mode
   4. `S1(config-line)# password c1$c0`  - Set the VTY password
   5. `S1(config-line)# login`  - Enable login on the VTY lines
* VTY lines are used to remotely connect to a switch using Telnet
   

### **IP Classes**  
   * First IP is Default Gateway & Last IP is Broadcast Address

| Class | Range   | Default Subnet Mask | Networks        | Hosts           |
| ----- | ------- | ------------------- | --------------- | -------------   |
| A     | 0-127   | 255.0.0.0           | 2^7 (128)       | 2^24 (16777216) |
| B     | 128-191 | 255.255.0.0         | 2^14 (16384)    | 2^16 (65536)    |
| C     | 192-223 | 255.255.255.0       | 2^21 (2097152)  | 2^8 (256)       |

 <br>
 
* Subnet - Breaks down a network into smaller networks
* Subnet Mask - Determines the network and host portions of an IP address     

---

<img src='./L2.png' /><br>
