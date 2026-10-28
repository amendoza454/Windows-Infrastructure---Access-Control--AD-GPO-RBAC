# Network Configuration

## Environment
* Domain: NMG.com
* Domain Controller: NMG-DC01
* Server OS: Windows Server 2019
* Workstation: NMG-WS01
* Client OS: Windows 11 Pro
* Virtualization: Oracle VirtualBox
* Internal Network: NMG-LAN

## Network Settings
| Setting | Domain Controller | Workstation |
|---|---|---|
| IPv4 Address | 192.168.50.10 | 192.168.50.20 |
| Subnet Mask | 255.255.255.0 | 255.255.255.0 |
| DNS Server | 192.168.50.10 | 192.168.50.10 |
| Internal Gateway | None | None |

## Domain Integration
* Joined NMG-WS01 to the NMG.com domain.
* Created a Workstations OU in Active Directory.
* Moved NMG-WS01 into the Workstations OU.
* Verified connectivity using ping and DNS SRV lookup.
* Confirmed successful domain authentication.

## Troubleshooting
* Corrected an incorrect workstation IP address and subnet mask.
* Verified network communication with 0% packet loss.
* Confirmed DNS discovery of NMG-DC01.

## Result
* Successfully integrated Windows 11 into the NMG Active Directory environment.
