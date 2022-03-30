# snmpdvcinfo - SNMP Device Information
--> Script for fetching Network Device Information via SNMP (Vendor, Hostname, Model, Version, Serial Number) <br />
--> Return Dict with following keys: 'dvc_vendor','dvc_hostname','dvc_model','dvc_version','dvc_sn' <br />
<br />
<br />
## Actual supported vendors:
--> Cisco support <br />
--> Fortinet Firewall support <br />
<br />
<br />
## Actual supported devices:
-> Cisco: <br />
--> Cisco Nexus   --> actual no hostname support<br />
--> Cisco Catalyst 2960X   --> actual no hostname support <br />
--> Cisco Catalyst 2960C <br />
--> Cisco Catalyst 3650   --> actual no hostname support <br />
--> Cisco Catalyst 3560 <br />
--> Cisco Catalyst 4500 Standalone   --> actual no hostname support<br />
--> Cisco Catalyst 4500 VSS   --> actual no hostname support<br />
--> Cisco Catalyst 1000   --> actual no hostname support <br />
--> Cisco Catalyst 4900   --> actual no hostname support <br />
--> Cisco Catalyst 9000   --> actual no hostname support <br />
--> Cisco Catalyst 6807   --> actual no hostname support Standalone <br />
--> Cisco Catalyst 6807 VSS   --> actual no hostname support <br />
<br />
-> Fortinet: <br />
--> Fortinet 3000D   --> actual no hostname support<br />
--> Fortinet 1500D   --> actual no hostname support<br />
--> Fortinet 600E   --> actual no hostname support<br />
--> Fortinet 500E   --> actual no hostname support<br />
--> Fortinet 300E   --> actual no hostname support<br />
<br />
<br />
## Usage Examples:
\>>> import snmpdvcinfo <br />
\>>>snmpdvcinfo.get_dvc_info("10.10.10.10","YOUR_SNMP-V2_COMMUNITY_STRING")  <br />
{'dvc_vendor': 'cisco', 'dvc_hostname': 'CoreSW1', 'dvc_model': 'C6807XL', 'dvc_version': 'Version 15.6(1)SY7', 'dvc_sn': 'ABSCSJWHD'}<br />
<br />
\>>>snmpdvcinfo.get_dvc_info("10.10.10.11","YOUR_SNMP-V2_COMMUNITY_STRING")  <br />
{'dvc_vendor': 'fortinet', 'dvc_hostname': 'firewallhostname', 'dvc_model': 'FGT_1500D', 'dvc_version': 'v7.8.1', 'dvc_sn': 'ABSCSJWHX'}<br />
<br />
## Error Examples:
<br />
No SNMP Connection possible:<br />
{'dvc_vendor': 'none', 'dvc_hostname': 'none', 'dvc_model': 'none', 'dvc_version': 'none', 'dvc_sn': 'none'}<br />
<br />
Cisco vendor detected but the device isn't supported:<br />
{'dvc_vendor': 'cisco', 'dvc_hostname': 'no_device_hostname', 'dvc_model': 'no_device_model', 'dvc_version': 'no_device_version', 'dvc_sn': 'no_device_sn'}

