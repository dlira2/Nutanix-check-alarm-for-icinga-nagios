# NUTANIX ALERT CHECK API ICINGA/NAGIOS v1.3

Alarm collector associated with the Nutanix AHV/VMware cluster and VM´s using NUTANIX API

Script to monitor the alarms of the Nutanix platform using API. It is necessary that the NAGIOS / ICINGA have connectivity to the IP of the Prism Element by port 9440. It is recommended not to use the "admin" user for the connection.
Tested on AOS 5.5.x , 5.8.x , 5.9.x and 5.10.x

Nutanix can be in the WARNING and CRITICAL state at the same time. That is why the script must be executed with the variable "--atype" to indicate that alarms of the CRITICAL or WARNING type are being searched. At the NAGIOS level it is recommended to generate 2 revisions for CRITICAL and WARNING alarms.

NOTE : When the administrator of the platform presses "resolve" the alarm, it will disappear in the output of the script.

Requirements:

python 3.6 or higher

Python Module :

     -import argparse 
     -import getpass 
     -import requests 
     -import urllib3 
     -import datetime 
     -import os 
     -import sys 
     
# HOW TO RUN SCRIPT EXAMPLE
CRITICAL :

     python NUTANIX_CHECK_API_v1.2.py --ip 10.26.1.139 --username someuser --password somepassword --atype CRITICAL

WARNING : 

     python NUTANIX_CHECK_API_v1.2.py --ip 10.26.1.139 --username someuser --password somepassword --atype WARNING


# EXAMPLE CONFIG IN ICINGA:

![alt text](https://github.com/dlira2/Nutanix-check-alarm-for-icinga-nagios/blob/master/HOST_PROFILE_ICINGA.png?raw=true)

# EXAMPLE OUTPUT CLUSTER NORMAL

![alt text](https://github.com/dlira2/Nutanix-check-alarm-for-icinga-nagios/blob/master/NUTANIX_OUTPUT_EXAMPLE%20NO%20ALARM.png?raw=true)

# EXAMPLE OUTPUT CLUSTER WARNING

![alt text](https://github.com/dlira2/Nutanix-check-alarm-for-icinga-nagios/blob/master/NUTANIX_OUTPUT_EXAMPLE_ALARM.png?raw=true)
