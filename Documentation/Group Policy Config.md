# Group Policy Configuration

## Environment
* Domain: NMG.com
* Domain Controller: NMG-DC01
* Target Workstation: NMG-WS01
* Organizational Unit: Workstations
* GPO Name: NMG - Workstation Security Baseline

## Problem
* NMG lacked a standardized workstation inactivity policy, increasing the risk of unattended computers remaining accessible.

## GPO Configuration
* Created a Workstations OU in Active Directory.
* Created and linked the Workstation Security Baseline GPO to the Workstations OU.
* Configured the following security setting:

| Setting | Configuration |
|---|---|
| Policy | Interactive logon: Machine inactivity limit |
| Location | Computer Configuration > Policies > Windows Settings > Security Settings > Local Policies > Security Options |
| Value | 900 seconds (15 minutes) |
| Target | Domain-joined workstations in the Workstations OU |

## Policy Deployment
* Moved NMG-WS01 into the Workstations OU.
* Executed gpupdate /force to refresh Group Policy.
* Used gpresult /scope computer /r to verify the applied GPO.
* Confirmed the inactivity timeout registry value was set to 900 seconds.

## Result
* Successfully deployed and verified the workstation inactivity security policy through Active Directory Group Policy.
