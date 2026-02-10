# Group Policy Labs (Windows Server 2019)

## Lab Overview
- Platform: VMware Workstation
- Domain: IDRISS.LOCAL
- Goal: Apply and verify Group Policy for user and computer restrictions in a domain environment.

## GPOs Implemented

### User Configuration (User Policies)
- Prevent access to the command prompt
- Disable Folder Options / File Explorer Options
- Show only specified Control Panel items (Fonts)

### Computer Configuration (Computer Policies)
- Removable Storage Access: deny read/write/execute
- Startup script: add a domain group/user to local Administrators (optional)

## Verification
- `gpupdate /force`
- `gpresult /r` (screenshots)

## Notes / Lessons Learned
- LSDOU order
- GPO refresh: 90 minutes + random offset
- Common troubleshooting: DNS/DHCP/APIPA impact on domain reachability
