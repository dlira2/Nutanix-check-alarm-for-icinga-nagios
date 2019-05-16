#Nutanix Check for icinga/nagios V1.1
Alarm collector associated with the Nutanix AHV cluster and VM´s using NUTANIX API

# NUTANIX ALERT CHECK API ICINGA/NAGIOS v1.1

Alarm collector associated with the Nutanix AHV cluster and VM´s.

Script to monitor the alarms of the Nutanix platform using API. It is necessary that the NAGIOS / ICINGA have connectivity to the IP of the Prism Element by port 9440. It is recommended not to use the "admin" user for the connection.
Tested on AOS 5.5.x , 5.8.x , 5.9.x and 5.10.x

Nutanix can be in the WARNING and CRITICAL state at the same time. That is why the script must be executed with the variable "--atype" to indicate that alarms of the CRITICAL or WARNING type are being searched. At the NAGIOS level it is recommended to generate 2 revisions for CRITICAL and WARNING alarms.

Requirements:

python 3.6 or higher

Python Module :
  import argparse
  import getpass
  import requests
  import urllib3
  import datetime
  import os
  import sys
