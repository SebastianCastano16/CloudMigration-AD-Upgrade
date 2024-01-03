---

# Active Directory Sandbox Environment

## Table of Contents
1. **Introduction**
2. **Testing & Results**
3. **Future of the Environment**
4. **Q&A**

## Introduction
Active Directory (AD) serves as a comprehensive data store for network objects such as servers, printers, users, and computer accounts. Security measures, including logon authentication and access control, are integrated into AD.

The current on-premises Active Directory is on Windows Server 2012R2, connected to Azure AD through Azure AD Connect version 1.6.16.0. With the end-of-life for Windows Server 2012R2 approaching, significant changes were tested to pave the way for server upgrades and a potential shift to a cloud-only environment.

## Testing & Results
### Objective
The primary goal was to replicate the existing sandbox/in-production Domain Controller while preparing for upgrades and a potential transition to a cloud-only setup.

### Steps Taken
- Setup of a physical server to act as the Domain Controller (Motherboard).
- Installation of Windows Server 2019 to mirror the active sandbox settings, including schema, user attributes, domain additions, etc.
- Backed up existing Group Policy Objects (GPOs) from the previous sandbox.
- Creation of an Azure tenant and installation of Azure AD Connect to establish on-premises network connectivity with the cloud.
- Testing of the environment for seamless operation of Active Directory and Azure AD Connect.

### New Organizational Units & Testing
Various tests were conducted involving user operations, group manipulations, attribute modifications, and administrative role assignments in both on-premises AD and Azure AD. These tests were replicated for both Windows Server 2012R2 and 2016 versions.

### Hybrid Environment Break to Cloud-Only
A step-by-step process was executed to transition users from a hybrid environment to a cloud-only setup. This involved creating and manipulating Organizational Units (OUs), adding/removing users, and demonstrating the transition using PowerShell and Azure UI.

### Transition Success
The tests showcased successful transitions of users into a cloud-only environment, including login functionality and password changes, indicating a seamless migration process.

## Future of the Environment
### Industry Movement
Many organizations, including TTD, are increasingly moving towards a cloud-only environment.

### Ongoing Work
Collaboration between the IT, Network, and Infrastructure teams is focused on transitioning users and network functionalities to a cloud-only setup. Considerations include VPN, Radius, domain controller decommissioning, and printer adjustments.

### Necessity of Change
The transition to a cloud-only environment is vital for long-term sustainability and aligns with industry trends for modernization.

---
