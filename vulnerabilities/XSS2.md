Affected Web App: PHPGurukul Hospital Management System

Version: v4.0

Title: Stored Cross Site Scripting (XSS) vulnerability

Affected Component: admin/query-details.php adminremark parameter within this file is vulnerable to stored cross-site scripting
admin/add-doctor.php docname parameter within this file is vulnerable to stored cross-site scripting

Impact: Cross-site scripting (XSS) vulnerability is a serious web security threat. When attackers execute this type of threat by injecting malicious scripts, it can lead to user data being compromised, their account getting hijacked, or even malware getting installed on the host machine.

Image:

Proof of Concept: To reproduce this attack, an attacker can inject a script into the Doctor Name field while adding new doctors in the admin/add-doctor.php file (as shown in the two figure above). The payload '<script>alert(1)</script>' was successfully accepted, leading to an alert being triggered for the user when the doctor is being viewed in admin/Manage-doctors.php

Proof of Concept: To reproduce this attack, an attacker can inject a script into the Admin Remark field while adding new queries. The payload '<script>alert(1)</script>' was successfully accepted, leading to an alert being triggered for the user when the doctor is being viewed in admin/unread-queries.php

Remediation: It is important to update the PHPGurukul Hospital Management System by properly sanitizing code variables and including restrictions for special characters so that malicious input such as the one shown in the example cannot be injected.
