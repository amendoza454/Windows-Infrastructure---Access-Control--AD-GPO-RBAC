
# Incident Report — NMG-0048

## Incident Summary
**Issue:** Active Directory Account Lockout  
**Affected User:** Jane Cooper (jcooper)  
**Department:** HR  
**Workstation:** NMG-WS01  
**Domain Controller:** NMG-DC01  
**Status:** Resolved

## Problem
Jane Cooper was unable to sign in to her Windows 11 workstation because her domain account was locked.

## Investigation
1. Confirmed the account lockout in Active Directory.
2. Investigated Windows Security logs using Event Viewer.
3. Located Event ID 4740 (Account Lockout).
4. Identified NMG-WS01 as the originating workstation.

## Root Cause
Repeated incorrect password attempts during a controlled troubleshooting simulation triggered the domain's account lockout policy.

## Corrective Action
Restored Jane Cooper's account access through Active Directory.

## Verification
- Successfully signed in as jcooper on NMG-WS01.
- Used `whoami` to verify domain authentication.
- Confirmed access was restored.

## Evidence
- Account lockout error
- Account lockout Group Policy configuration
- Event ID 4740 investigation
- Successful sign-in verification

## Skills Demonstrated
- Active Directory user administration
- Group Policy configuration
- Windows Event Viewer
- Account lockout troubleshooting
- Incident documentation
