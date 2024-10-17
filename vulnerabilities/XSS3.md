Affected Web App: PHPGurukul Hospital Management System

Version: v4.0

Title: Stored Cross Site Scripting (XSS) vulnerability

Affected Component: admin/add-doctor.php, admin/edit-doctor.php docname parameter within each of these files is vulnerable to stored Cross-Site Scripting

Impact: Cross-site scripting (XSS) vulnerability is a serious web security threat. When attackers execute this type of threat by injecting malicious scripts, it can lead to user data being compromised, their account getting hijacked, or even malware getting installed on the host machine.

Image:

<img width="909" alt="hospital_vul2_pic1" src="https://github.com/user-attachments/assets/ed075a80-c4e3-45e7-899f-9e2c23856d29">

<img width="913" alt="hospital_vul2_pic2" src="https://github.com/user-attachments/assets/c88e3610-c9f0-4f0e-a0fc-41e689720c1e">

Proof of Concept: To reproduce this attack, an attacker can inject a script into the Doctor Name field while adding a doctor in the admin/add-doctor.php file or while editing a doctor in the admin/edit-doctor.php file (as shown in the two figures above) under the Doctors tab of the application. The payload '<script>alert(1)</script>' was successfully accepted, leading to an alert being triggered for the user when the patients are being viewed in the file admin/Manage-doctors.php

<img width="909" alt="hospital_vul2_pic3" src="https://github.com/user-attachments/assets/b51dc22f-9ff0-4375-a2e7-c3e3aa1548a7">


Remediation: It is important to update the PHPGurukul Hospital Management System by properly sanitizing code variables and including restrictions for special characters so that malicious input such as the one shown in the example cannot be injected.
