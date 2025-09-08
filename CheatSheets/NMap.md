# Basic Scans

### Single Scan : ``nmap [target]``
### Multi Scan : ``nmap [target 1, target 2 .... target n]``
### List Scan : ``nmap -iL [list.txt]``
### IP Range Scan : ``nmap [range of IP addresses]``
### Aggressive Scan : ``nmap -A [target]``
### IPv6 Scan : ``nmap -6 [target]``

# Discovery Scans

### Ping Scan : ``nmap -sP [target]``
### TCP SYN Ping : ``nmap -PS [target]``
### TCP ACK Ping: ``nmap -PA [target]``
### UDP Ping: ``nmap -PU [target]``
### Force Reverse TCP: ``nmap -R [target]``
### Alt DNS Lookup: ``nmap –system-dns [target]``

# Port Scans

### TCP SYN port scan (Default): ``nmap 192.168.1.1 -sS``
### TCP connect port scan : ``nmap 192.168.1.1 -sT``
### UDP port scan: ``nmap 192.168.1.1 -sU``
### TCP ACK port scan: ``nmap 192.168.1.1 -sA``

# Firewall Evasion

### Fragment packets: ``nmap -f [target]``
### Zombie Scan: ``nmap -sI [zombie] [target]``
### Spoof Mac Scan: ``nmap –spoof-mac [MAC|0|vendor] [target]``

# Version Detection

### OS Detection: ``nmap -O [target]``
### Service Version Detection: ``nmap -sV [target]``


PS: To view more scans, refer to the [[https://www.geeksforgeeks.org/ethical-hacking/nmap-cheat-sheet/]] [[https://www.stationx.net/nmap-cheat-sheet/]]

