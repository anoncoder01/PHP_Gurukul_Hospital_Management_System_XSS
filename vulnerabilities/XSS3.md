Affected Web App: PHPGurukul Hospital Management System

Version: v4.0

Title: Stored Cross Site Scripting (XSS) vulnerability

Affected Component: /admin/query-details.php, affected parameter: adminremark within this file is vulnerable to stored Cross-Site Scripting, /doctor/edit-profile.php, affected parameter: docname within this file is vulnerable to stored Cross-Site Scripting

Impact: Cross-site scripting (XSS) vulnerability is a serious web security threat. When attackers execute this type of threat by injecting malicious scripts, it can lead to user data being compromised, their account getting hijacked, or even malware getting installed on the host machine.

Image:


<img width="907" alt="hospital_vul3_pic2" src="https://github.com/user-attachments/assets/3da92413-1883-4f85-908f-907df1394955">


Proof of Concept: In order to exploit the vulnerability, an attacker can inject a script like <script>alert(1)</script> into the Admin Remark field of /admin/query-details.php or the Doctor Name field of /doctor/edit-profile.php. The XSS will be triggered in /admin/query-details.php for the first XSS and locations where the created doctor is viewed like admin/Manage-doctors.php for the second XSS

<img width="909" alt="hospital_vul2_pic3" src="https://github.com/user-attachments/assets/e33b40dc-a948-4666-8327-0906fb6b9151">

<img width="908" alt="hospital_vul3_pic1" src="https://github.com/user-attachments/assets/fefcb58f-3e38-4d82-8dbd-a59d52aba6ed">


Remediation: It is important to update the PHPGurukul Hospital Management System by properly sanitizing code variables and including restrictions for special characters so that malicious input such as the one shown in the example cannot be injected.
