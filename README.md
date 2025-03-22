# Cybersecurity-Portfolio
## Professional Statement
 As a cybersecurity professional, I protect organizations from evolving cyber threats while upholding integrity and compliance with legal standards. With strong analytical and problem-solving skills, I specialize in security monitoring, threat analysis, and incident response. My expertise includes identifying vulnerabilities, implementing security controls, and educating stakeholders on cyber risks. I am proficient in leveraging security tools such as SIEMs, SQL, Python, IDS/IPS, and firewalls to detect and mitigate threats effectively. Passionate about continuous learning, I stay updated on emerging attack vectors and best practices to enhance security resilience.
## Project description (Linux Commands to Manage Files)
This project aims to examine and manage file permissions in the file system. As a security analyst in the research team, I am to determine if the file permission matches the authorization given. If they don't match, then I will modify the permissions to authorize the appropriate user.
### Step 1 Describe Permission String
![File permissions](https://github.com/user-attachments/assets/a5313aa5-c2c6-4264-85a2-af522a7272b0)

In the above screenshot, it can be seen that the file ``project_k.txt`` in the ``/home/researcher2/projects`` directory has permission as such ``rw-rw-rw-``. This means that each user; user, group, and others, they are allowed to access the file and modify it but is not allowed to execute any executable file. In more detail, the first string of permission ``rw-`` in the above, describes the user's permission allowing it to only read and write the file while the dash shows that the user isn't allowed to execute any executable file. The same applies to the other user groups.
