# Evidence Index – Student ID 2416509

Complete figure register for CSO7018 Final Assessment. All figures use sequential numbering Fig00–Fig30 with unique filenames and real lab screenshots.

| Figure | Filename | Section | Purpose | Key Evidence |
|---|---|---|---|---|
| Fig00 | Evidence/00_Topology/Fig00_Lab_Topology.png | Lab Topology | Controlled lab network diagram | Kali 192.168.56.101, Ubuntu 192.168.56.103, host-only network |
| Fig01 | Evidence/01_Lab_Setup_and_Service_Validation/Fig01_Ubuntu_Target_IP_Configuration.png | Lab Setup | Ubuntu target IP configuration | `ip a` on enp0s3: 192.168.56.103/24 |
| Fig02 | Evidence/01_Lab_Setup_and_Service_Validation/Fig02_Kali_Attacker_IP_Configuration.png | Lab Setup | Kali attacker IP configuration | `ip a` on eth0: 192.168.56.101/24 (real screenshot) |
| Fig03 | Evidence/01_Lab_Setup_and_Service_Validation/Fig03_SSH_Service_Status.png | Lab Setup | SSH service validation | OpenSSH active |
| Fig04 | Evidence/01_Lab_Setup_and_Service_Validation/Fig04_Apache_Service_Status.png | Lab Setup | Apache service validation | Apache/2.4.66 active |
| Fig05 | Evidence/01_Lab_Setup_and_Service_Validation/Fig05_Ping_Connectivity_Test.png | Lab Setup | Network reachability | ICMP success attacker to target |
| Fig06 | Evidence/01_Lab_Setup_and_Service_Validation/Fig06_Nmap_Service_Discovery.png | Lab Setup | Service discovery | Ports 22 and 80 open |
| Fig07 | Evidence/01_Lab_Setup_and_Service_Validation/Fig07_Apache_Web_Service_Access.png | Lab Setup | Web service access | Apache default page reachable |
| Fig08 | Evidence/02_Finding_1_SSH_Weak_Authentication/Fig08_SSH_Login_Success.png | Finding 1 | SSH login validation | Successful remote SSH access |
| Fig09 | Evidence/02_Finding_1_SSH_Weak_Authentication/Fig09_TestUser_Creation.png | Finding 1 | Test account creation | testuser account created |
| Fig10 | Evidence/02_Finding_1_SSH_Weak_Authentication/Fig10_Hydra_Credential_Discovery.png | Finding 1 | Credential attack | testuser:password123 discovered |
| Fig11 | Evidence/02_Finding_1_SSH_Weak_Authentication/Fig11_SSH_Authentication_Logs.png | Finding 1 | SSH journal analysis | journalctl: failed/successful auth from 192.168.56.101 |
| Fig12 | Evidence/03_Finding_2_Apache_Enumeration/Fig12_HTTP_Header_Disclosure_Before_Hardening.png | Finding 2 | Pre-hardening HTTP headers | `curl -I`: Server: Apache/2.4.66 (Ubuntu) (real screenshot) |
| Fig13 | Evidence/03_Finding_2_Apache_Enumeration/Fig13_Nikto_Web_Server_Assessment_Before_Hardening.png | Finding 2 | Nikto assessment | Version disclosure, missing headers |
| Fig14 | Evidence/03_Finding_2_Apache_Enumeration/Fig14_DIRB_Directory_Enumeration.png | Finding 2 | Directory enumeration | /index.html, /server-status |
| Fig15 | Evidence/03_Finding_2_Apache_Enumeration/Fig15_Apache_Access_Log_Analysis.png | Finding 2 | Access log analysis | Dirb/Nikto requests from attacker IP |
| Fig16 | Evidence/03_Finding_2_Apache_Enumeration/Fig16_Apache_Error_Log_Analysis.png | Finding 2 | Error log analysis | Blocked sensitive path requests |
| Fig17 | Evidence/04_Finding_2_Apache_Mitigation_Retest/Fig17_Apache_Hardening_Configuration.png | Finding 2 Mitigation | Apache security.conf | ServerTokens Prod, ServerSignature Off, TraceEnable Off |
| Fig18 | Evidence/04_Finding_2_Apache_Mitigation_Retest/Fig18_Apache_Headers_Module_Enabled.png | Finding 2 Mitigation | Headers module | a2enmod headers |
| Fig19 | Evidence/04_Finding_2_Apache_Mitigation_Retest/Fig19_Custom_Security_Headers_Enabled.png | Finding 2 Mitigation | Custom headers conf | Security headers enabled |
| Fig20 | Evidence/04_Finding_2_Apache_Mitigation_Retest/Fig20_Apache_Config_Test.png | Finding 2 Mitigation | Config validation | apache2ctl configtest Syntax OK |
| Fig21 | Evidence/04_Finding_2_Apache_Mitigation_Retest/Fig21_Apache_Restart_Status.png | Finding 2 Mitigation | Service restart | Apache restarted successfully |
| Fig22 | Evidence/04_Finding_2_Apache_Mitigation_Retest/Fig22_Apache_Security_Headers_Verification.png | Finding 2 Re-test | curl -I after hardening | Server: Apache; security headers present |
| Fig23 | Evidence/04_Finding_2_Apache_Mitigation_Retest/Fig23_Nikto_Retest_After_Hardening.png | Finding 2 Re-test | Nikto reassessment | Reduced findings; Server: Apache |
| Fig24 | Evidence/05_Finding_1_SSH_Mitigation_Retest/Fig24_Open_Ports_Verification.png | Finding 1 Mitigation | Port verification | SSH 22 and Apache 80 listening |
| Fig25 | Evidence/05_Finding_1_SSH_Mitigation_Retest/Fig25_Fail2Ban_Service_Status.png | Finding 1 Mitigation | Fail2Ban service | fail2ban active (running) |
| Fig26 | Evidence/05_Finding_1_SSH_Mitigation_Retest/Fig26_Fail2Ban_Global_Status.png | Finding 1 Mitigation | Fail2Ban global status | sshd jail active |
| Fig27 | Evidence/05_Finding_1_SSH_Mitigation_Retest/Fig27_Fail2Ban_SSH_Jail_Status.png | Finding 1 Mitigation | SSH jail status | sshd jail monitoring |
| Fig28 | Evidence/05_Finding_1_SSH_Mitigation_Retest/Fig28_Strong_Password_Verification.png | Finding 1 Mitigation | Password hardening | passwd and chage -l verification |
| Fig29 | Evidence/05_Finding_1_SSH_Mitigation_Retest/Fig29_SSH_Login_With_Strong_Password.png | Finding 1 Re-test | Strong password login | Successful login after remediation |
| Fig30 | Evidence/05_Finding_1_SSH_Mitigation_Retest/Fig30_Hydra_Retest_After_Mitigation.png | Finding 1 Re-test | Hydra retest | 0 valid passwords found |

## Figure Caption Reference

| Figure | Caption |
|---|---|
| 0 | Controlled penetration testing lab topology showing the Kali attacker VM, Ubuntu target VM, VirtualBox host-only network, assessed services, and rules of engagement. |
| 1 | Ubuntu target IP configuration showing 192.168.56.103 on the host-only lab network. |
| 2 | Kali attacker IP configuration showing 192.168.56.101 on the host-only lab network. |
| 3 | SSH service status confirming OpenSSH is active on the Ubuntu target. |
| 4 | Apache service status confirming Apache HTTP Server is active on the Ubuntu target. |
| 5 | Ping connectivity test confirming network reachability between the Kali attacker and Ubuntu target. |
| 6 | Nmap service discovery identifying OpenSSH on TCP port 22 and Apache HTTP on TCP port 80. |
| 7 | Browser access confirming Apache default web page availability. |
| 8 | Successful SSH login validating remote access to the Ubuntu target. |
| 9 | Creation of the testuser account used for controlled credential testing. |
| 10 | Hydra credential attack identifying the weak SSH credential testuser:password123. |
| 11 | SSH journal logs showing failed authentication attempts, successful authentication, and source IP evidence from the Kali attacker. |
| 12 | HTTP response headers before hardening showing Apache version disclosure. |
| 13 | Nikto web server assessment identifying Apache information disclosure and missing HTTP security headers. |
| 14 | DIRB directory enumeration identifying accessible resources including index.html and server-status. |
| 15 | Apache access logs showing enumeration activity from the Kali attacker IP address. |
| 16 | Apache error logs showing invalid URI paths, blocked requests, and attempted access to sensitive paths. |
| 17 | Apache security configuration updated with ServerTokens Prod, ServerSignature Off, and TraceEnable Off. |
| 18 | Apache headers module enabled to support HTTP security header configuration. |
| 19 | Custom Apache security headers configuration enabled. |
| 20 | Apache configuration test confirming Syntax OK after hardening changes. |
| 21 | Apache restarted successfully after security hardening changes. |
| 22 | Curl verification showing reduced server disclosure and newly applied HTTP security headers. |
| 23 | Nikto reassessment after Apache hardening showing reduced findings and reduced server information disclosure. |
| 24 | Open ports verification showing SSH and Apache services listening on the Ubuntu target. |
| 25 | Fail2Ban service status confirming the defensive control is active. |
| 26 | Fail2Ban global status showing active jail monitoring. |
| 27 | Fail2Ban SSH jail status confirming SSH monitoring. |
| 28 | Password hardening verification for the testuser account. |
| 29 | Successful SSH login using the strengthened password after remediation. |
| 30 | Hydra retest after remediation showing no valid password found. |
