# SMB & NTFS Permissions Configuration

## Environment
* Domain: NMG.com
* File Server: NMG-DC01
* Server OS: Windows Server 2019
* Shared Folder Location: C:\NMG-Shares
* Protocol: Server Message Block (SMB)
* Access Control: NTFS Permissions and Active Directory Security Groups

## Problem
* NMG lacked centralized departmental file storage with properly restricted access. Without appropriate permissions, employees could potentially access sensitive information belonging to other departments.

## Folder Structure
* Created C:\NMG-Shares on NMG-DC01.
* Created 4 departmental folders:
  * Finance
  * HR
  * IT
  * Operations

## NTFS Permissions
* Disabled permission inheritance on each departmental folder.
* Converted inherited permissions into explicit permissions.
* Removed generic NMG\Users permission entries.
* Assigned department-specific security groups Modify permissions.
* Retained administrative Full Control permissions.

| Department | Security Group | NTFS Permission |
|---|---|---|
| Finance | Finance-Users | Modify |
| HR | HR-Users | Modify |
| IT | IT-Users | Modify |
| Operations | Operations-Users | Modify |

## SMB Share Configuration
* Enabled Advanced Sharing for each departmental folder.
* Created separate SMB shares for Finance, HR, IT, and Operations.
* Removed the default Everyone share permission.
* Assigned department security groups Change and Read permissions.
* Granted Administrators Full Control.

| Share Name | Network Path | Authorized Group | Share Permissions |
|---|---|---|---|
| Finance | \\NMG-DC01\Finance | Finance-Users | Change, Read |
| HR | \\NMG-DC01\HR | HR-Users | Change, Read |
| IT | \\NMG-DC01\IT | IT-Users | Change, Read |
| Operations | \\NMG-DC01\Operations | Operations-Users | Change, Read |

## Access Control Testing
* Signed in to NMG-WS01 using a simulated HR employee account.
* Successfully accessed the HR network share.
* Confirmed access was denied to Finance, IT, and Operations shares.
* Verified file creation, modification, and deletion within the authorized HR share.

## Result
* Implemented centralized departmental file sharing using SMB and NTFS permissions.
* Enforced department-based access restrictions through Active Directory security groups.
* Verified authorized file access and denial of unauthorized access.
