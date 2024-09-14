Affected Web App: PHPGurukul Hospital Management System

Version: v4.0

Title: Stored Cross Site Scripting (XSS) vulnerability

Affected Component: doctor/add-patient.php, doctor/edit-patient.php patname parameter, pataddress parameter, and medhis parameter within each of these files is vulnerable to stored Cross-Site Scripting

Impact: Cross-site scripting (XSS) vulnerability is a serious web security threat. When attackers execute this type of threat by injecting malicious scripts, it can lead to user data being compromised, their account getting hijacked, or even malware getting installed on the host machine.

Image:

Proof of Concept: To reproduce this attack, an attacker can inject a script into the Patient Name field, the Patient Address field, or the Medical History field while adding a patient in the doctor/add-patient.php file or while editing new members in the doctor/edit-patient.php file (as shown in the two figures above) under the Patients tab of the application. The payload '<script>alert(1)</script>' was successfully accepted, leading to an alert being triggered for the user when the patients are being viewed in multiple files such as doctor/manage-patient.php or admin/manage-patient.php or admin/view-patient.php

Remediation: It is important to update the PHPGurukul Hospital Management System by properly sanitizing code variables and including restrictions for special characters so that malicious input such as the one shown in the example cannot be injected.
