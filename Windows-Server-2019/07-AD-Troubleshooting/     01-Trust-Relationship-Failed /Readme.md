# Trust Relationship Failed – Windows 11 Domain Workstation

## Issue Description

User reported inability to log into domain account on a Windows 11 workstation.

**Error displayed:**

> "The trust relationship between this workstation and the primary domain failed."

Machine was previously joined to domain: **idriss.local**  
User unable to access network resources.

---

## Root Cause

A machine account secure channel password mismatch occurred between the workstation and Active Directory.

When the computer account password stored locally does not match the password stored in AD, the secure channel breaks and domain authentication fails.

---

## Resolution (Method Used)

1. Logged in using local administrator account.  
2. Removed workstation from domain and joined a temporary workgroup.  
3. Rebooted the workstation.  
4. Rejoined workstation to domain **idriss.local** using domain admin credentials.  
5. Rebooted again.  
6. Verified domain login successful.

---

## Screenshots

### 1) Trust Relationship Error
![Trust Error](Screenshots/01-trust-error.png)

### 2) Join Temporary Workgroup
![Join Workgroup](Screenshots/03-join-workgroup.png)

### 3) Rejoin Domain
![Rejoin Domain](Screenshots/04-rejoin-domain.png)

### 4) Domain Login Verified

Command used:

```cmd
whoami
```

Output:

```cmd
idriss0\mohammed.zondy
```

![Domain Login Success](Screenshots/05-domain-success.png)

---

## Jira Ticket (ITSM Documentation)

This incident was documented in Jira using a Kanban workflow:

To Do → In Progress → Resolved

### 5) Jira Ticket – Created (To Do Status)
![Jira Ticket To Do](Screenshots/06-jira-ticket-todo.png)

### 6) Jira Ticket – In Progress
![Jira Ticket In Progress](Screenshots/07-jira-ticket-inprogress.png)

### 8) Jira Ticket – Resolved Status
![Jira Ticket Resolved](Screenshots/08-jira-ticket-resolved.png)

