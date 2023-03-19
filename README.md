# observium-syslogng
Observium Syslog NG enrichment

You might want to change this:

```
2023-03-19 07:48:29 	fw 	Informational (6) 	FILTERLOG 4,,,1000000103,re0,match,block,in,4,0x0,,127,6695,0,DF,6,tcp,71,192.168.4.18,170.72.231.161,51471,443,31,FPA,1578095462:1578095493,2626363609,513,,
2023-03-19 07:48:26 	fw 	Informational (6) 	FILTERLOG 4,,,1000000103,re0,match,block,in,4,0x0,,127,6693,0,DF,6,tcp,71,192.168.4.18,170.72.231.161,51471,443,31,FPA,1578095462:1578095493,2626363609,513,,
2023-03-19 07:48:25 	fw 	Informational (6) 	FILTERLOG 4,,,1000000103,re0,match,block,in,4,0x0,,127,6685,0,DF,6,tcp,71,192.168.4.18,170.72.231.161,51471,443,31,FPA,1578095462:1578095493,2626363609,513,,
2023-03-19 07:48:24 	fw 	Informational (6) 	FILTERLOG 4,,,1000000103,re0,match,block,in,4,0x0,,127,6683,0,DF,6,tcp,71,192.168.4.18,170.72.231.161,51471,443,31,FPA,1578095462:1578095493,2626363609,513,,
2023-03-19 07:48:24 	fw 	Informational (6) 	FILTERLOG 4,,,1000000103,re0,match,block,in,4,0x0,,127,6677,0,DF,6,tcp,71,192.168.4.18,170.72.231.161,51471,443,31,FPA,1578095462:1578095493,2626363609,513,,
2023-03-19 07:48:24 	fw 	Informational (6) 	FILTERLOG 4,,,1000000103,re0,match,block,in,4,0x0,,127,6672,0,DF,6,tcp,40,192.168.4.18,170.72.231.161,51471,443,0,FA,1578095493,2626363609,513,,
2023-03-19 07:48:24 	fw 	Informational (6) 	FILTERLOG 4,,,1000000103,re0,match,block,in,4,0x0,,127,6671,0,DF,6,tcp,71,192.168.4.18,170.72.231.161,51471,443,31,PA,1578095462:1578095493,2626363609,513,,
2023-03-19 07:48:24 	fw 	Informational (6) 	FILTERLOG 4,,,1000000103,re0,match,block,in,4,0x0,,127,6670,0,DF,6,tcp,68,192.168.4.18,170.72.231.161,51410,443,28,PA,779989134:779989162,1391324290,515,,
2023-03-19 07:15:35 	fw 	Informational (6) 	FILTERLOG 4,,,1000000103,re0,match,block,in,4,0x0,,63,46001,0,DF,6,tcp,76,192.168.4.19,142.250.184.106,49014,443,24,FPA,2248031179:2248031203,1161691067,361,,nop;nop;TS
2023-03-19 07:15:26 	fw 	Informational (6) 	FILTERLOG 4,,,1000000103,re0,match,block,in,4,0x0,,63,46000,0,DF,6,tcp,76,192.168.4.19,142.250.184.106,49014,443,24,FPA,2248031179:2248031203,1161691067,361,,nop;nop;TS
2023-03-19 07:15:24 	fw 	Informational (6) 	FILTERLOG 4,,,1000000103,re0,match,block,in,4,0x0,,63,45999,0,DF,6,tcp,76,192.168.4.19,142.250.184.106,49014,443,24,FPA,2248031179:2248031203,1161691067,361,,nop;nop;TS
2023-03-19 07:15:23 	fw 	Informational (6) 	FILTERLOG 4,,,1000000103,re0,match,block,in,4,0x0,,63,45998,0,DF,6,tcp,76,192.168.4.19,142.250.184.106,49014,443,24,FPA,2248031179:2248031203,1161691067,361,,nop;nop;TS
2023-03-19 07:15:23 	fw 	Informational (6) 	FILTERLOG 4,,,1000000103,re0,match,block,in,4,0x0,,63,45997,0,DF,6,tcp,52,192.168.4.19,142.250.184.106,49014,443,0,FA,2248031203,1161691067,361,,nop;nop;TS
```
...into this:

![pfSense filterlog](https://i.ibb.co/BCfZ4jq/Screenshot-2023-03-19-at-10-42-08-Observium-Syslog.png)

## Table of Contents
- [Observium Syslog NG enrichment](#observium-syslog-ng-enrichment)
  - [Installation](#installation)
  - [Usage](#usage)
  - [Further developments](#further-developments)
  - [Credits](#credits)

## Installation
Apply the observium-proxmox.diff to add support for generic highlights (MAC addresses, IP addresses and hashes), Mikrotik firewall logs and Netgate/pfSense filterlog.
```
cd /opt/observium
patch -p2 -N < observium-syslogng.diff
```

## Usage

You don't need to do anything other, simply enjoy visualizing syslogs :-)

## Further developments

Netgate/pfSense support have to needs to be improved (more informations could be visualized). Other plugins could be developed and put into $OBSERVIUM_HOME/html/includes/print/custom; contributions are welcome!

## Credits

Andrea Tuccia "wildstray"

