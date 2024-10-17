Affected Web App: PHPGurukul Hospital Management System

Version: v4.0

Title: Stored Cross Site Scripting (XSS) vulnerability

Affected Component: doctor/add-patient.php, doctor/edit-patient.php patname parameter, pataddress parameter, and medhis parameter within each of these files is vulnerable to stored Cross-Site Scripting

Impact: Cross-site scripting (XSS) vulnerability is a serious web security threat. When attackers execute this type of threat by injecting malicious scripts, it can lead to user data being compromised, their account getting hijacked, or even malware getting installed on the host machine.

Image:

<img width="910" alt="hospital_vul1_pic1" src="https://github.com/user-attachments/assets/ebf82ab7-cf1c-4b81-b469-d770bc464fdf">

<img width="912" alt="hospital_vul1_pic2" src="https://github.com/user-attachments/assets/84a9d7e1-ab68-4056-801c-599516b29b69">


Proof of Concept: To reproduce this attack, an attacker can inject a script into the Patient Name field, the Patient Address field, or the Medical History field while adding a patient in the doctor/add-patient.php file or while editing a patient in the doctor/edit-patient.php file (as shown in the two figures above) under the Patients tab of the application. The payload '<script>alert(1)</script>' was successfully accepted, leading to an alert being triggered for the user when the patients are being viewed in multiple files such as doctor/manage-patient.php or admin/manage-patient.php or admin/view-patient.php

<img width="910" alt="hospital_vul1_pic3" src="https://github.com/user-attachments/assets/7b78aaa1-3bb1-42a8-a24b-41e6671996f0">

<img width="913" alt="hospital_vul1_pic4" src="https://github.com/user-attachments/assets/710c801d-9b31-4af3-b09d-d464ac00361a">

<img width="911" alt="hospital_vul1_pic5" src="https://github.com/user-attachments/assets/d634058e-d860-4e16-aa2e-df6ffe6c6071">

Remediation: It is important to update the PHPGurukul Hospital Management System by properly sanitizing code variables and including restrictions for special characters so that malicious input such as the one shown in the example cannot be injected.
