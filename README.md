# SDM72D-Modbus v2
SDM72D-Modbus v2 is a 3-phase power meter with RS485 Port modbus RTU. 
This is a plugin for domoticz to get all the data from the meter directly into Domoticz. 
To make it work usually you need a USB-Modbus dongle plugged into raspberry and cables connected to A and B in the meter. 
This is a Modbus RTU communication, does not work with TCP-IP Modbus.

Original code by MFxMF for the SDM630-M power meter https://github.com/MFxMF/SDM630-Modbus
Further edited by bbossink to work with SDM72 v1 and by philips to work with SDM72d-m v2.

This version is addapted to SDM72d-m v2 which, comparing to v1, report separetly power on L1, L2 and L3, reactive power and many other grid parameters.
More info can be found in the modbus manual of this energy meter: https://stromzähler.eu/media/pdf/93/17/d7/SDM72DM-V2.pdf

Requirements: <br>
Working Domoticz instance with working python plugin service (see logs in domoticz)<br>
Used python modules: <br>
pyserial -> https://pythonhosted.org/pyserial/ <br>
minimalmodbus -> http://minimalmodbus.readthedocs.io<br>
If python plugin service is not working try :
sudo apt-get update
sudo apt-get install python3.7 libpython3.7 python3.7-dev -y"<br>
sudo apt-get install python-pip python3-pip -y
pip install pyserial
pip install minimalmodbus
sudo pip3 install -U pymodbus
sudo reboot
<br>
Installation: <br>
cd ~/domoticz/plugins<br>
git clone https://github.com/philip-s/SDM72D-Modbus-v2-Domoticz-plugin.git <br>
After installation restart domoticz: 
systemctl restart domoticz.service <br>
<br>
Configuration: <br>
Select "Eastron SDM72-D-Modbus v2" in Hardware configuration screen.<br>
If needed modify some parameters (defaults will do) and click add.<br>
Hint: Set reading interval to 0 if you want updates per "heartbeat" of the system (aprox 10s in my case).<br>
<br>
Many new devices will be automatically added. 
Go to devices tab, there you will find all ofthem and add the one you need to your system (usually not all of them are necessary).<br>
<br>
Tested on domoticz v2020.2 (v1) and 2021.1 (v2)
<br><br><br>


