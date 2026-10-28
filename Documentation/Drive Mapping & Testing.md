# Drive Mapping & Access Testing

## Environment
* Domain: NMG.com
* Domain Controller: NMG-DC01
* Workstation: NMG-WS01
* GPO Name: NMG - Department Drive Mapping
* Configuration Tool: Group Policy Management
* Drive Mapping Method: Group Policy Preferences (GPP)

## Problem
* NMG employees needed consistent access to departmental network shares without manually entering network paths. Drive access also needed to be restricted according to employee department and security group membership.

## Group Policy Configuration
* Created the NMG - Department Drive Mapping GPO.
* Linked the GPO to the NMG.com domain.
* Navigated to User Configuration > Preferences > Windows Settings > Drive Maps.
* Created 4 mapped drive entries using the Update action.
* Enabled Reconnect for each drive.
* Configured item-level targeting using Active Directory security groups.

## Department Drive Mappings

| Department | Drive Letter | Network Path | Security Group |
|---|---|---|---|
| HR | H: | \\NMG-DC01\HR | HR-Users |
| Finance | F: | \\NMG-DC01\Finance | Finance-Users |
| IT | I: | \\NMG-DC01\IT | IT-Users |
| Operations | O: | \\NMG-DC01\Operations | Operations-Users |

## Group Policy Deployment
* Executed gpupdate /force on the Windows 11 workstation.
* Signed out and signed back in using simulated employee accounts.
* Verified that departmental network drives appeared automatically in File Explorer under This PC.

## Employee Access Testing
* HR employee received the H: drive.
* Finance employee received the F: drive.
* IT employee received the I: drive.
* Operations employee received the O: drive.
* Confirmed employees received only their authorized departmental drive mappings.
* Verified that unauthorized departmental share access was denied during HR employee testing.

## File Permission Testing
* Signed in using an authorized HR employee account.
* Created a test text file inside the HR mapped drive.
* Successfully modified and saved the file.
* Successfully deleted the test file.
* Confirmed the assigned SMB and NTFS permissions allowed the intended operations.

## Result
* Successfully automated network drive mapping for all 4 departments.
* Implemented security group-based targeting through Group Policy Preferences.
* Verified successful drive mapping and departmental access restrictions.
* Demonstrated centralized file access management in a simulated enterprise environment.
