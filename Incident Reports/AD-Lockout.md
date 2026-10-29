

# Day 6 — Incident Report: NMG-0048

## Incident Summary

**Ticket:** NMG-0048  
**Issue:** Active Directory Account Lockout  
**Affected User:** Jane Cooper (`jcooper`)  
**Department:** HR  
**Workstation:** NMG-WS01  
**Domain Controller:** NMG-DC01  
**Status:** Resolved  

## 1. Incident Description

Jane Cooper reported being unable to sign in to her Windows 11 workstation due to an account lockout.

The objective was to investigate the authentication failure, identify its source, restore account access, and verify successful domain authentication.

![Original Help Desk Ticket](../evidence/Day-6_Jira_Ticket_NMG-0048.png)

## 2. Issue Reproduction

Simulated repeated incorrect password attempts for Jane Cooper on NMG-WS01.

The workstation displayed authentication errors, and the domain account was eventually locked.

![Account Lockout](../evidence/Day-6_jcooper_Account_Lockout.png)

## 3. Group Policy Configuration

Configured the domain's account lockout policy through Group Policy Management.

**Configured settings:**
- Account lockout threshold: 5 attempts
- Account lockout duration: 15 minutes
- Reset lockout counter after: 15 minutes
- Allow Administrator account lockout: Disabled

![Account Lockout GPO](../evidence/Day-6_Account_Lockout_GPO.png)

## 4. Investigation

Used Event Viewer on NMG-DC01 to investigate the account lockout.

**Findings:**
- Event ID: 4740
- Event Description: A user account was locked out
- Affected Account: `jcooper`
- Caller Computer: NMG-WS01

The security event identified the workstation associated with the lockout.

![Event Viewer Event 4740](../evidence/Day-6_EventID_4740.png)

## 5. Root Cause

Repeated incorrect password attempts triggered the Active Directory account lockout policy.

The issue was intentionally reproduced in an isolated lab environment to simulate a real help desk incident.

## 6. Corrective Action

Restored Jane Cooper's account access and verified her account was no longer locked.

![Account Unlocked](../evidence/Day-6_AD_AccountUnlock.png)

## 7. Resolution Verification

Successfully signed in to NMG-WS01 using Jane Cooper's domain credentials.

Verified the authenticated account using:

```cmd
whoami
```

**Expected result:** `nmg\jcooper`

![Successful Login Verification](../evidence/Day-6_Ticket_Resolved_Login_Verification.png)

**Final Status:** Resolved

## 8. Skills Demonstrated

- Active Directory account administration
- Group Policy Management
- Windows Event Viewer
- Security Event ID 4740 analysis
- Windows 11 authentication troubleshooting
- Incident investigation and documentation
- Resolution verification
