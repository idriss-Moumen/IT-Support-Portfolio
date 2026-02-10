# Group Policy Labs (Windows Server 2019)

## Lab Overview
This lab demonstrates the use of Group Policy Objects (GPOs) to control user behavior and system access in a Windows Server 2019 Active Directory environment.

The policies were applied to the **HR Organizational Unit (OU)** to simulate real-world user restrictions commonly used in enterprise environments.

---

## Environment
- Platform: VMware Workstation
- Server OS: Windows Server 2019
- Client OS: Windows 10
- Domain: IDRISS.LOCAL

---

## GPO Design and Scope
- GPOs are linked to the **HR OU**
- User Configuration policies apply to HR users regardless of the computer used
- Computer Configuration policies apply to domain-joined machines
- Policy inheritance and scope were verified using Group Policy Management Console (GPMC)

---

## Implemented Group Policies

### 1. Disable Command Prompt (User Policy)
Command Prompt access was disabled to prevent users from executing command-line tools.

**Policy used:**
- User Configuration → Administrative Templates → System  
- Prevent access to the command prompt

**Result:**
Users receive a message indicating that Command Prompt has been disabled by the administrator.

![CMD Disabled](Screenshots/client-cmd-disabled.png)

---

### 2. Restrict Control Panel to Fonts Only (User Policy)
Control Panel access was restricted so users can only access the Fonts applet.

**Policy used:**
- User Configuration → Administrative Templates → Control Panel  
- Show only specified Control Panel ite
