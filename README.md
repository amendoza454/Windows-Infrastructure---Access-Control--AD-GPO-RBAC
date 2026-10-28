# Windows Infrastructure & Access Control (AD)(GPO)(RBAC)

## Project Overview
* Expanded Northstar Medical Group's (NMG) simulated Active Directory environment to practice Windows workstation integration, Group Policy management, network file sharing, and access control. This project demonstrates hands-on experience with Windows Server 2019, Windows 11, Active Directory, Group Policy Objects (GPOs), and NTFS permissions.

## Problem Statement
* NMG's fictional IT environment lacked standardized workstation security policies and centralized departmental file sharing. Without automated drive mapping and properly configured access permissions, employees could experience inconsistent access to company resources and potential exposure of sensitive departmental information.

## Solution Overview
* I deployed a Windows 11 workstation (NMG-WS01) and joined it to the NMG.com Active Directory domain. After configuring internal networking and DNS connectivity, I created a Workstations OU and implemented a Group Policy Object (GPO) enforcing a 15-minute inactivity limit. I then configured 4 departmental SMB network shares (Finance, HR, IT, and Operations), applying NTFS and share permissions through existing Active Directory security groups. Using Group Policy Preferences, I automated departmental drive mapping based on security group membership. Finally, I tested employee access across all 4 departments, verified unauthorized access was denied, and confirmed file creation, modification, and deletion permissions.

## Video Walkthrough
* Coming Soon

## Tools Used
* Windows Server 2019 - Domain Controller and File Sharing
* Windows 11 Pro - Domain-Joined Employee Workstation
* Active Directory Domain Services (AD DS) - Domain and Security Group Management
* Group Policy Management - Workstation Security and Drive Mapping
* SMB and NTFS - Network File Sharing and File Permissions
* DNS - Domain Controller Discovery and Name Resolution
* Oracle VirtualBox - Virtualized Lab Environment
* GitHub - Project Documentation and Evidence

## Project Timeline
* Day 5: Windows 11 deployment, network configuration, and domain integration
* Day 5: Workstation OU creation and Group Policy security baseline
* Day 5: DNS troubleshooting and GPO application verification
* Day 6: Departmental SMB share creation and NTFS permission configuration
* Day 6: Automated drive mapping using Group Policy Preferences
* Day 6: Employee access testing and permission validation

## Key Accomplishments
* Deployed and joined a Windows 11 workstation to the NMG.com domain
* Implemented a workstation security GPO with a 15-minute inactivity limit
* Configured 4 departmental SMB shares with NTFS and share-level permissions
* Automated 4 departmental network drive mappings using security group targeting
* Verified authorized access and restricted unauthorized departmental access
* Successfully tested file creation, modification, and deletion through a mapped network drive
