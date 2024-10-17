Affected Web App: PHPGurukul Hospital Management System

Version: v4.0

Title: Stored Cross Site Scripting (XSS) vulnerability

Affected Component: /admin/query-details.php, affected parameter: adminremark within this file is vulnerable to stored Cross-Site Scripting, /doctor/edit-profile.php, affected parameter: docname within this file is vulnerable to stored Cross-Site Scripting

Impact: Cross-site scripting (XSS) vulnerability is a serious web security threat. When attackers execute this type of threat by injecting malicious scripts, it can lead to user data being compromised, their account getting hijacked, or even malware getting installed on the host machine.

Image:




Proof of Concept: In order to exploit the vulnerability, an attacker can inject a script like <script>alert(1)</script> into the Admin Remark field of /admin/query-details.php or the Doctor Name field of /doctor/edit-profile.php. The XSS will be triggered in /admin/query-details.php for the first XSS and locations where the created doctor is viewed like admin/Manage-doctors.php for the second XSS



Remediation: It is important to update the PHPGurukul Hospital Management System by properly sanitizing code variables and including restrictions for special characters so that malicious input such as the one shown in the example cannot be injected.
