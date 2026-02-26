# Microsoft 365 Administration Lab

## Overview
This lab demonstrates hands-on administration tasks performed in a Microsoft 365 tenant environment. The objective was to simulate real-world enterprise scenarios including user onboarding, license management, role delegation, Exchange Online mailbox configuration, and offboarding procedures.

This lab focuses on practical Microsoft 365 administration using Entra ID (Azure AD) and Exchange Online.

---

## Environment

- Microsoft 365 Business Standard (Trial Tenant)
- Entra ID (Cloud Identity)
- Exchange Online
- Microsoft 365 Admin Center

Tenant Domain:
`idrisslabs.onmicrosoft.com`

---

## Skills Demonstrated

- Tenant setup and initial configuration
- User provisioning in Entra ID
- License assignment and removal
- Service impact validation (Exchange Online provisioning)
- Role-Based Access Control (User Administrator role)
- Shared mailbox creation and delegation
- Mailbox permission configuration (Full Access, Send As)
- Offboarding workflow:
  - Block sign-in
  - Convert mailbox to shared
  - License removal
- Understanding of Cloud Identity vs On-Prem Active Directory

---

## Lab Modules

1. Tenant Setup  
2. User and License Management  
3. Shared Mailbox Configuration  
4. Role-Based Access Control (RBAC)  
5. Mailbox Permissions and Offboarding Workflow  

---

## Key Learning Outcomes

This lab strengthened understanding of:

- Modern cloud identity management
- Microsoft 365 licensing structure
- Exchange Online mailbox architecture
- Delegated access vs credential sharing
- Security best practices in user lifecycle management
- Differences between Azure AD Join and traditional Domain Join

---

## Architecture Perspective

This lab demonstrates a cloud-only identity model where:

- Entra ID acts as the identity authority
- Exchange Online provides mailbox services
- Licensing controls service provisioning
- Role delegation enforces least-privilege access

This reflects modern enterprise cloud administration practices.
