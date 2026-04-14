# CMMC Level 1 Reference Guide

**Author:** Brent Camp  
**Version:** 1.0  
**Purpose:** Plain-language reference guide for all 15 FAR 52.204-21 / CMMC Level 1 controls, including what to show, how to implement it, and what evidence to collect.

---

## How to Use This Guide

Each control section includes:
- **What we need to show** — the plain-language objective of the control
- **How to implement it** — specific tools and methods organized by sub-requirement
- **Evidence examples** — what documentation satisfies the control during an assessment

This guide is designed for small businesses and DoD contractors preparing for CMMC Level 1 compliance. It is not a substitute for official CMMC documentation but serves as a practical starting point for gap assessments and policy development.

---

## Controls Index

| Control ID | Domain | Title |
|---|---|---|
| AC.L1-b.1.i | Access Control | Authorized Access Control |
| AC.L1-b.1.ii | Access Control | Transaction and Function Control |
| AC.L1-b.1.iii | Access Control | External Connections |
| AC.L1-b.1.iv | Access Control | Control Public Information |
| IA.L1-b.1.v | Identification and Authentication | Identification |
| IA.L1-b.1.vi | Identification and Authentication | Authentication |
| MP.L1-b.1.vii | Media Protection | Media Disposal |
| PE.L1-b.1.viii | Physical Protection | Limit Physical Access |
| PE.L1-b.1.ix | Physical Protection | Manage Visitors and Physical Access |
| SC.L1-b.1.x | System and Communications Protection | Boundary Protection |
| SC.L1-b.1.xi | System and Communications Protection | Public Access System Separation |
| SI.L1-b.1.xii | System and Information Integrity | Flaw Remediation |
| SI.L1-b.1.xiii | System and Information Integrity | Malicious Code Protection |
| SI.L1-b.1.xiv | System and Information Integrity | Update Malicious Code Protection |
| SI.L1-b.1.xv | System and Information Integrity | System and File Scanning |

---

## Access Control

### AC.L1-b.1.i — Authorized Access Control

**What we need to show:**  
System access is restricted so that only authorized users, approved automated processes, and approved devices are permitted to access company systems and information.

**How to implement it:**

**(a) Authorized users are identified**  
Active Directory, Azure AD, local user accounts, employee badges

**(b) Processes acting on behalf of authorized users are identified**  
Microsoft Defender, CrowdStrike, Acronis

**(c) Devices authorized to connect are identified**  
Company laptops, servers, approved mobile devices

**(d) System access is limited to authorized users**  
User accounts with passwords, multi-factor authentication, role-based access policy

**(e) System access is limited to processes acting on behalf of authorized users**  
Role-based access controls, Group Policies defined in a central user management system

**(f) System access is limited to authorized devices**  
Network Access Control (NAC) or firewall rules to restrict access (e.g. pfSense with allow/deny policies)

---

### AC.L1-b.1.ii — Transaction and Function Control

**What we need to show:**  
System access is limited so users can only perform the transactions and functions they are approved to perform.

**How to implement it:**

**(a) The types of transactions and functions users are permitted to execute are defined**  
Job roles with defined access levels (e.g. office staff vs. accounting vs. management), written role permissions specifying who can approve, pay, change, or delete records. These must be clearly defined.

**(b) System access is limited to defined transaction types for authorized users**  
Role-based access control in Active Directory or Entra ID, permissions set in Microsoft 365 or SharePoint

---

### AC.L1-b.1.iii — External Connections

**What we need to show:**  
Connections to external systems are identified, verified, and limited so only approved and necessary external access is allowed.

**How to implement it:**

**(a) Connections to external systems are identified**  
Inventory of all external systems documented in a network diagram and network security documentation (e.g. VPN connections, cloud services, third-party vendors, remote access tools)

**(b) The use of external systems is identified**  
Conduct assessments to determine how each external system is utilized. For smaller companies this can be done by an MSP.

**(c) Connections to external systems are verified**  
Automated log scans of connected network devices to ensure they are correct and legitimate. Audits can be performed on network connections for companies with an IT department.

**(d) The use of external systems is verified**  
Login auditing, role-based access, access reviews. A SIEM system supports this. Smaller companies can outsource to a managed SIEM provider.

**(e) Connections to external systems are controlled and limited**  
Firewall allow/deny rules, VPN access restrictions, IP allowlists, network segmentation outlined in the network diagram and access control policies

**(f) The use of external systems is controlled and limited**  
Least-privilege access, approved applications only, disabled unauthorized services outlined in the access control policy

---

### AC.L1-b.1.iv — Control Public Information

**What we need to show:**  
Information posted or processed on publicly accessible systems is controlled so Federal Contract Information (FCI) is not exposed.

**How to implement it:**

**(a) Individuals authorized to post or process information on publicly accessible systems are identified**  
Designated staff roles, website admins, marketing or communications personnel defined in a content management policy

**(b) Procedures to ensure FCI is not posted on publicly accessible systems are identified**  
Written policies prohibiting FCI posting, employee training on handling FCI

**(c) A review process is in place prior to posting content to publicly accessible systems**  
Manager or supervisor approval, content review workflows, approval checklists before publishing

**(d) Content on publicly accessible systems is reviewed to ensure it does not include FCI**  
Periodic content reviews, scheduled audits of public websites or platforms, documented review results

**(e) Mechanisms are in place to remove and address improper posting of FCI**  
Incident response procedures, immediate content removal plans, corrective actions and retraining if needed

**Common Examples of FCI:**
- Technical details in a government-issued Request for Proposal (RFP)
- Internal timelines or schedules for government projects
- System or infrastructure diagrams related to a contract (even if not marked CUI)
- Vendor quotes or pricing submitted to a government agency (unless publicly posted)

---

## Identification and Authentication

### IA.L1-b.1.v — Identification

**What we want to show:**  
Users, processes, and devices accessing company systems are uniquely identified.

**How to implement it:**

**(a) System users are identified**  
Active Directory, Microsoft Entra ID (Azure AD), local user accounts, employee IDs or badges  
*Evidence: User Directory Document*

**(b) The identity of each process acting on behalf of a user is authenticated before system access**  
Antivirus software, backup services, system update services  
*Evidence: Process monitoring logs*

**(c) Devices accessing the system are identified**  
Company laptops, desktops, servers, approved mobile devices  
*Evidence: Device inventory report*

---

### IA.L1-b.1.vi — Authentication

**What we want to show:**  
Verify the identity of users, processes, or devices as a prerequisite to allowing access to organizational information systems.

**How to implement it:**

**(a) The identity of each user is authenticated before system access**  
Usernames and passwords, Active Directory  
*Evidence: Multi-factor authentication policy*

**(b) The identity of each process acting on behalf of a user is authenticated before system access**  
Approved service accounts, authenticated system services, security and backup software running under verified accounts  
*Evidence: Device management system, access control policies*

**(c) The identity of each device is authenticated before system access**  
Domain-joined devices, device certificates, approved VPN connections  
*Evidence: User access logs, device management system documents*

---

## Media Protection

### MP.L1-b.1.vii — Media Disposal

**What we want to show:**  
Sanitize or destroy information system media containing Federal Contract Information before disposal or release for reuse.

**How to implement it:**

**(a) System media containing FCI is sanitized or destroyed before disposal**  
Physical destruction of hard drives and storage media, shredding services, certified destruction vendors, destruction logs  
*Evidence: Media disposal policy, destruction log records*

**(b) System media containing FCI is sanitized before release for reuse**  
Data wiping using approved software, overwrite processes, sanitization certificates, documented reuse procedures  
*Evidence: Sanitization certificates, audit reports*

---

## Physical Protection

### PE.L1-b.1.viii — Limit Physical Access

**What we need to show:**  
Limit physical access to organizational information systems, equipment, and operating environments to authorized individuals.

**How to implement it:**

**(a) Authorized individuals allowed physical access are identified**  
Access control lists, employee badges, key card assignment  
*Evidence: Key card access logs, access control list*

**(b) Physical access to organizational systems is limited to authorized individuals**  
Locked server room, key card or badge access  
*Evidence: Photos of a locked room are sufficient evidence*

**(c) Physical access to equipment is limited to authorized individuals**  
Locked equipment rooms, restricted cabinets, controlled access to networking and computer equipment  
*Evidence: Photos are sufficient*

**(d) Physical access to operating environments is limited to authorized individuals**  
Locked doors, security checkpoints, visitor sign-in logs, escorted access procedures  
*Evidence: These controls will be outlined in an Access Control Policy*

---

### PE.L1-b.1.ix — Manage Visitors and Physical Access

**What we need to show:**  
Escort visitors and monitor visitor activity; maintain audit logs of physical access; and control and manage physical access devices.

**How to implement it:**

**(a) Visitors are escorted**  
Visitor sign-on procedures, visitor badges, employee escorts  
*Evidence: Visitor logbook*

**(b) Visitor activity is monitored**  
Escort supervision, security cameras in common areas, staff awareness of visitor presence  
*Evidence: Access control logs, records of visitors coming and going*

**(c) Audit logs of physical access are maintained**  
Visitor logs, badge or key card logs  
*Evidence: Visitor access logs*

**(d) Physical access devices are identified**  
Badges, keycards, keys, fobs, access codes  
*Evidence: Access control logs*

**(e) Physical access devices are controlled**  
Documentation showing activation, deactivation, and restriction of badges, keycards, or access codes  
*Evidence: Device issuance logs*

**(f) Physical access devices are managed**  
Records showing who was issued which device and associated access levels  
*Evidence: Audit reports*

---

## System and Communications Protection

### SC.L1-b.1.x — Boundary Protection

**What we need to show:**  
Monitor, control, and protect organizational communications at the external boundaries and key internal boundaries of the information systems.

**How to implement it:**

**(a) The external system boundary is defined**  
Network diagrams, documented firewall locations, defined internet-facing connections  
*Evidence: Network diagram*

**(b) Key internal system boundaries are defined**  
Network segmentation documentation, VLANs, internal firewall boundaries, separation of sensitive systems  
*Evidence: Network diagram, access control policies*

**(c) Communications are monitored at the external system boundary**  
Firewall logs, intrusion detection or prevention systems, traffic monitoring alerts  
*Evidence: Firewalls with logging capabilities*

**(d) Communications are monitored at key internal boundaries**  
Internal firewall logs, inter-VLAN traffic monitoring  
*Evidence: Network segmentation documentation or network diagram*

**(e) Communications are controlled at the external system boundary**  
Firewall allow/deny rules, access control lists, port and protocol restrictions  
*Evidence: Screenshots of firewall configurations are sufficient*

**(f) Communications are controlled at key internal boundaries**  
Role-based access controls between segments, internal firewall rules, restricted lateral movement  
*Evidence: ACLs, use of monitoring tools*

**(g) Communications are protected at the external system boundary**  
Encrypted connections, secure VPNs, TLS-protected services, firewall-based threat protection  
*Evidence: Use of encryption protocols like TLS or VPN*

**(h) Communications are protected at key internal boundaries**  
Encrypted internal traffic where applicable, secure inter-system communication, protected management interfaces  
*Evidence: Encryption protocols*

---

### SC.L1-b.1.xi — Public Access System Separation

**What we need to show:**  
Implement subnetworks for publicly accessible system components that are physically or logically separated from internal networks.

**How to implement it:**

**(a) Publicly accessible system components are identified**  
Internet-facing systems such as web servers, email servers, and externally accessible applications documented in asset inventories and network diagrams  
*Evidence: Asset management system, network diagram*

**(b) Subnetworks for publicly accessible system components are physically or logically separated from internal networks**  
Dedicated public-facing subnets, DMZ, VLAN separation, firewall rules restricting traffic between public and internal networks  
*Evidence: VLAN configuration, network segmentation documentation, ACLs*

---

## System and Information Integrity

### SI.L1-b.1.xii — Flaw Remediation

**What we need to show:**  
Identify, report, and correct information and information system flaws in a timely manner.

**How to implement it:**

**(a) The timeframe to identify system flaws is specified**  
Defined timelines documented in policies based on severity or system criticality  
*Evidence: Incident response or vulnerability management policy*

**(b) System flaws are identified within the specified timeframe**  
Regular monitoring, vulnerability scanning, security alerts, periodic system reviews  
*Evidence: Vulnerability scanning reports*

**(c) The timeframe to report system flaws is specified**  
Reporting timelines defined in incident response or escalation procedures (e.g. within 24 hours of becoming aware)  
*Evidence: Internal reporting policies*

**(d) System flaws are reported within the specified timeframe**  
Issue tracking tickets, incident reports, internal notifications to IT or management  
*Evidence: Issue tracking system logs*

**(e) The timeframe to correct system flaws is specified**  
Patch and remediation timelines documented by priority or security level  
*Evidence: Patch management and remediation policies*

**(f) System flaws are corrected within the specified timeframe**  
Patch installation records, remediation tracking, closed tickets with completion dates  
*Evidence: Remediation logs showing corrective action*

**Flaw Remediation Implementation Methods:**
- **Physical Isolation** — System is not connected to other systems by any means. Inaccessible without physical presence.
- **Logical Isolation** — System is physically connected but a protocol or device blocks all communication to and from it.
- **Patching** — An update that resolves a security issue, adds features, or fixes functionality.
- **Restricted Access to Authorized Users** — Strong authentication mechanisms, authorization controls, or physical/logical controls provide implicit protection.

---

### SI.L1-b.1.xiii — Malicious Code Protection

**What we need to show:**  
Provide protection from malicious code at appropriate locations within organizational information systems.

**How to implement it:**

**(a) Designated locations for malicious code protection are identified**  
Email gateways, web servers, file servers, workstations, laptops, mobile devices, systems exposed to the internet  
*Evidence: Network diagrams, asset management records*

**(b) Protection from malicious code at designated locations is provided**  
Antivirus and endpoint protection software, email filtering, firewall protections  
*Evidence: Email filtering logs, web application firewall logs, patch management*

**Types of Malicious Code:**
- **Virus** — Malicious code that performs a destructive function on a local network or device
- **Worm** — Like a virus but self-replicates and can infect other computers through internet or LAN connections without user interaction
- **Spyware** — Runs in the background and records downloads, sites visited, and personal information
- **Logic Bomb** — Triggered when a specific set of criteria is met (e.g. when a new user is entered into Active Directory). Difficult to protect against and detect.
- **Adware** — Infects a device with constant unwanted ads after visiting a particular website
- **Backdoor Malware** — Any way an attacker can bypass normal security applications to gain high-level access on the network, a software application, or computer

---

### SI.L1-b.1.xiv — Update Malicious Code Protection

**What we need to show:**  
Update malicious code protection mechanisms when new releases are available.

**How to implement it:**

**(a) Malicious code protection mechanisms are updated when new releases are available**  
Automatic antivirus and anti-malware definition updates, centrally managed update policies, scheduled update checks, alerts for failed updates, review of update logs  
*Evidence: An update policy, automated update logs, centralized logging reports*

---

### SI.L1-b.1.xv — System and File Scanning

**What we need to show:**  
Perform periodic scans of the information system and real-time scans of files from external sources as files are downloaded, opened, or executed.

**How to implement it:**

**(a) The frequency for malicious code scans is defined**  
Document scanning schedules, written security or scanning policies defining scan intervals, risk-based scan frequency definitions  
*Evidence: Scan logs or scanning policy document*

**(b) Malicious code scans are performed with the defined frequency**  
Automated scheduled scans, scan execution logs, timestamps showing scans ran as required  
*Evidence: Scan logs*

**(c) Real-time malicious code scans of files from external sources are performed**  
Endpoint protection with real-time scanning enabled, email attachment scanning, downloads scanned from web or cloud services  
*Evidence: Compliance audit reports, incident reports, or endpoint protection configurations*

---

## Additional Resources

- [CMMC Official Documentation](https://www.acq.osd.mil/cmmc/)
- [FAR 52.204-21 Full Text](https://www.acquisition.gov/far/52.204-21)
- [NIST SP 800-171 (CUI Protection Reference)](https://csrc.nist.gov/publications/detail/sp/800-171/rev-2/final)

---

*This guide was developed based on practical CMMC Level 1 advisory work with DoD contractors. It is intended as a reference tool and starting point for compliance preparation, not as legal or official compliance guidance.*

*Author: Brent Camp | github.com/BrentCamp*
