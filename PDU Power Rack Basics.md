###  Commands to login in PDU power rack:
Steps you will need in order to assign a static address to rack.
1. Make sure your network port on rack is connected to a Network.
2. You need to telnet into the step 1 address example : telnet 10.20.172.39
3. It will ask for login/pwd which is apc/apc.
3. You can manually look at screen on rack and check what is your ip address you are currently connected to.
4. Type tcpip command to get the info about your current network, it will output something like following,:
    tcpip:
    Ouput you will get looks like following:


   Active IPv4 Settings
   --------------------
   Active IPv4 Address:          10.20.172.39
   Active IPv4 Subnet Mask:      255.255.248.0
   Active IPv4 Gateway:          10.20.168.1
   
4.apc>tcpip -?(Gives all the useful commands you can use here for example setting ip/gateway etc)

Usage: tcpip  -- Configure and display TCP/IP v4 parameters
    tcpip [-S <enable | disable>]
          [-i <ipv4 address>]
          [-s <subnet mask>]
          [-g <gateway>]
          [-d <domain name>]
          [-h <host name>]
5.type:tcpip -i 10.20.168.191(Changing the ip address from 10.20.172.39 to 10.20.168.191)
6.type:tcpip -s 255.255.248.0  (Giving a gateway,it is usually same for organization)
7.type:tcpip ig  10.20.681
8.You need to reboot your switch, in order to do that you can just type: reboot and wait for your rack to get reboot.
9.Verify the changes that you have made manually on rack by going into networks and matching it the new ip address.
    
    


```python
System Commands:
---------------------------------------------------------------------------
For command help: command ?

?           about       alarmcount  boot        bye         cd
clrrst      console     date        delete      dir         dns
email       eventlog    exit        firewall    format      ftp
help        lang        lastrst     ledblink    logzip      netstat
ntp         ping        portspeed   prompt      pwd         quit
radius      reboot      resetToDef  session     smtp        snmp
snmptrap    snmpv3      system      tcpip       tcpip6      user
userdflt    web         whoami      xferINI     xferStatus

Device Commands:
---------------------------------------------------------------------------
bkLowLoad   bkNearOver  bkOverLoad  bkReading   bkPeakCurr  bkRestrictn
devLowLoad  devNearOver devOverLoad devReading  devPeakLoad devStartDly
dispID      humLow      humMin      humHyst     humReading  lcd
lcdBlink    olAssignUsr olCancelCmd olDlyOff    olDlyOn     olDlyReboot
olGroups    olName      olOff       olOffDelay  olOn       olOnDelay
olRbootTime olReboot    olStatus    olUnasgnUsr phLowLoad   phNearOver
phOverLoad  phReading   phPeakCurr  phRestrictn prodInfo    sensorName
tempHigh    tempMax     tempHyst    tempReading userAdd     userDelete
userList    userPasswd  energyWise
```
