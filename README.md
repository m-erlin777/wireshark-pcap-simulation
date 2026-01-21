# Malicious Network Traffic Analysis
Simulating network events with Wireshark and Kali and mapping MITRE ATT&amp;CK.

# Overview
### Architecture
- ```Kali VM + Nmap```
- ```Windows Host + Wireshark```

### Scenarios
- Remote System Discovery ```MITRE T1018```

Attacker VM sends ICMP echo requests to see if host is alive and responsive.
```
ping <windows_ip>
```

- Network Service Discovery ```MITRE T1046```

Sequential TCP SYN scan, simulating stealth port scan behavior.
```
nmap -sS <windows_ip>
```

- Network Share Discovery ```MITRE T1135```

SMB negotiations, a common precursor for lateral movement within the network.
```
nmap --script smb-protocols <windows_ip>
smbclient -L //<windows_ip> -N
```

- Application Layer Availability (C2) ```MITRE T1071.001 ```

HTTP(S) GET service availability test.
```
curl http://<windows_ip>
curl https://<windows_ip>
```




