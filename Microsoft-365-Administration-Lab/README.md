# Microsoft 365 Administration Lab

## Overview
This lab documents hands-on administrative tasks performed in a Microsoft 365 cloud tenant. The goal was to simulate real-world enterprise scenarios including user onboarding, license management, role delegation, shared mailbox configuration, and offboarding workflow procedures.

The lab was performed in a cloud-only environment using Entra ID and Exchange Online.

---

## Environment

- Microsoft 365 Business Standard (Trial Tenant)
- Entra ID (Azure AD)
- Exchange Online
- Microsoft 365 Admin Center

Tenant Domain:
`idrisslabs.onmicrosoft.com`

---

## Skills Demonstrated

- Tenant creation and initial configuration
- User provisioning in Entra ID
- License assignment and validation of service provisioning
- License removal and verification of mailbox service impact
- Role-Based Access Control (User Administrator role assignment)
- Shared mailbox creation and member assignment
- Mailbox permission configuration (Full Access and Send As)
- User offboarding workflow simulation:
  - Block sign-in
  - Convert mailbox to shared
  - License removal
- Understanding of cloud identity vs traditional on-prem Active Directory

---

## Key Learning Outcomes

- How Microsoft 365 licensing controls service provisioning
- Differences between User Mailboxes and Shared Mailboxes
- Delegated access vs password sharing
- Role-based access design using least privilege principles
- Architecture differences between Azure AD Join and traditional Domain Join
