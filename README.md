---

# Project README

## Overview
This project focuses on upgrading the Windows Server environment from 2012R2 to 2016, specifically targeting the domain and forest function levels. Additionally, it includes testing Azure AD synchronization using Azure AD Connect.

## Objective
The primary goal is to demonstrate a step-by-step process for upgrading the on-premises Active Directory domain and functional levels, Azure AD Connect, and transitioning towards a cloud-only environment.

## Testing Notes
### Windows Server 2016 Upgrade
- Raising Domain & Forest Function Level:
  - Initially attempted through AD Domain and Trusts, discovered both levels wouldn't raise simultaneously.
  - Raised domain functional level first; later raised forest functional level separately.

### Azure AD Sync Testing
- Verified basic functions successfully synced with Azure AD.
- Tested functionalities for:
  - Users/User Attributes
  - Groups
  - Roles within On-Prem AD and Azure AD

### AAD Connect Break
- Accidentally set AAD Connect to Auto Upgrade, disrupting synchronization.
- Steps taken:
  - Removed AAD Connect
  - Downgraded on-prem AD forest and domain functional levels back to 2012
  - Reinstalled an older version (1.6.16.0) of AAD Connect

### Challenges Encountered
- Removing AAD Connect broke sync between on-prem and Azure.
- Attempts to reconnect failed, resulting in login issues and authentication errors.

### Identified Issue
- Suspected cached data hindering Azure's ability to authenticate due to the disrupted connection.

### Resolution and Final Outcome
- After several attempts, restored the environment to 2016 functional levels and AAD Connect version 2.1.16.0.
- Successfully reestablished synchronization between on-prem AD and Azure AD.

### Cloud-Only Testing
- Conducted tests segregating Cloud-Only OUs from sync.
- Successfully moved users between OUs, observed sync behavior with Azure AD.

## Conclusion
The project achieved the primary objective of demonstrating upgrades from 2012R2 to 2016 and synchronization with Azure AD. Challenges were faced and resolved, providing insights into potential issues during such upgrades.

---
