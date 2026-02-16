# 05 – DHCP Server Implementation and Troubleshooting

## 📌 Lab Overview

This lab demonstrates the deployment, configuration, and troubleshooting of the DHCP role on a Windows Server Domain Controller within a VMware isolated environment.

The goal of this lab was not only to configure DHCP successfully, but also to understand and resolve common DHCP-related issues such as scope misconfiguration and client APIPA addressing.

---

## 🖥️ Lab Environment

- Hypervisor: VMware Workstation
- Network Type: Host-only
- Network Subnet: 192.168.36.0 /24
- Domain Controller (DC) IP: 192.168.36.130 (Static)
- DNS Server: 192.168.36.130
- DHCP Scope Range: 192.168.36.100 – 192.168.36.254

The DHCP server was installed directly on the Domain Controller and integrated with Active Directory.

---

## ⚙️ DHCP Role Installation

The DHCP role was installed via Server Manager.

After installation:
- Post-install configuration was completed
- DHCP server was authorized in Active Directory
- IPv4 scope was created

![DHCP Installation](Screenshots/DHCP-Installation.png)

---

## 🚨 Issue 1 – Incorrect Scope Network (196 instead of 192)

Initially, the DHCP scope was incorrectly configured as:

196.168.36.0 /24

This did not match the actual server network (192.168.36.0 /24).

Because of this mismatch:
- The DHCP server could not properly lease addresses
- Clients failed to receive valid IP addresses

![Wrong Scope](Screenshots/DHCP-Wrong-Scope-196-Network.png)

---

## 🛠 Resolution – Scope Correction

The incorrect scope was deleted and recreated properly:

Network: 192.168.36.0 /24  
Start IP: 192.168.36.100  
End IP: 192.168.36.254  

The scope was then activated.

![Correct Scope](Screenshots/DHCP-Correct-Scope-192-Network.png)

---

## 🚨 Issue 2 – APIPA Address (169.254.x.x)

Before correcting the scope configuration, the client received an APIPA address:

169.254.x.x

APIPA (Automatic Private IP Addressing) occurs when:
- The client broadcasts a DHCP request
- No DHCP server responds

This confirmed a DHCP configuration issue.

![APIPA Wrong Scope](Screenshots/Client-APIPA-Wrong-Scope.png)

---

## ✅ Successful DHCP Lease

After correcting the scope configuration, the client successfully received a valid IP address from the DHCP server.

The assigned IP address fell within the configured scope range.

![DHCP Success](Screenshots/Client-DHCP-Lease-Success.png)

The lease was verified inside the DHCP console:

![Lease Console](Screenshots/DHCP-Address-Lease-Console.png)

---

## 🔐 DHCP Reservation

A DHCP reservation was configured using the client’s MAC address to ensure the device always receives the same IP address.

Reservation IP: 192.168.36.120

![Reservation](Screenshots/DHCP-Reservation-Configuration.png)

After renewing the lease, the client successfully received the reserved IP address.

![Reserved IP](Screenshots/Client-Reserved-IP-Verification.png)

---

## 🔒 DHCP Filtering (Deny Test)

To test DHCP filtering behavior, the client MAC address was added to the DHCP Deny filter list.

![Deny Filter](Screenshots/DHCP-Deny-Filter-Configuration.png)

After applying the deny filter:
- The client was unable to obtain an IP address
- The system assigned an APIPA address (169.254.x.x)

![APIPA Deny](Screenshots/Client-APIPA-Deny-Filter.png)

This confirmed that DHCP filtering was functioning correctly.

---

## 📚 Technical Concepts Demonstrated

- DHCP broadcast behavior
- DHCP scope creation and activation
- Scope-network alignment importance
- Understanding APIPA (169.254.x.x)
- DHCP authorization in Active Directory
- DHCP reservations based on MAC address
- DHCP Allow/Deny filtering
- Lease verification via DHCP console

---

## ✅ Final Outcome

The DHCP server is fully operational and integrated with Active Directory.

All of the following were successfully tested:

- Dynamic IP address assignment
- Lease confirmation
- Scope correction troubleshooting
- Reservation enforcement
- MAC-based DHCP filtering

This lab demonstrates both deployment and troubleshooting skills in a Windows Server infrastructure environment.


