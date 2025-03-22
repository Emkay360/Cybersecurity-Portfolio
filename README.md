# Cybersecurity-Portfolio
## Professional Statement
 As a cybersecurity professional, I protect organizations from evolving cyber threats while upholding integrity and compliance with legal standards. With strong analytical and problem-solving skills, I specialize in security monitoring, threat analysis, and incident response. My expertise includes identifying vulnerabilities, implementing security controls, and educating stakeholders on cyber risks. I am proficient in leveraging security tools such as SIEMs, SQL, Python, IDS/IPS, and firewalls to detect and mitigate threats effectively. Passionate about continuous learning, I stay updated on emerging attack vectors and best practices to enhance security resilience.
## Project description (Linux Commands to Manage Files)
This project aims to examine and manage file permissions in the file system. As a security analyst in the research team, I am to determine if the file permission matches the authorization given. If they don't match, then I will modify the permissions to authorize the appropriate user.
### Step 1: Describe Permission String
![File permissions](https://github.com/user-attachments/assets/a5313aa5-c2c6-4264-85a2-af522a7272b0)

In the above screenshot, it can be seen that the file ``project_k.txt`` in the ``/home/researcher2/projects`` directory has permission set as ``rw-rw-rw-`` in the Linux command interface. This means that each user; user, group, and others, is allowed to access the file and modify it but is not allowed to execute any executable file. In more detail, the first string of permission ``rw-`` in the above, describes the user's permission allowing it to only read and write the file while the dash shows that the user isn't allowed to execute any executable file. The same applies to the other user groups.
### Step 2: Change File Permissions
The organization does not allow others to have write access to any files. Based on the permissions established in the previous step, I modified the permissions on the above file ``project_k.txt`` using the following steps

- I typed the command ``ls -l`` to reveal all 5 files, a sub-directory, and their permissions.
  
![Files and directories](https://github.com/user-attachments/assets/eb8ae506-2d09-44d8-b579-707e2ee7a4ce)

- I then typed ``chmod o-w project_k.txt``
- Lastly, after changing their permission I typed ``ls -l`` to view the modified permissions and it changed to ``rw-rw-r--``
 ### Step 3: Change File Permissions on Hidden Files
 The research team has archived ``.project_x.txt``. Also, this file should not have written permission for anyone, but the user and group should be able to read the file. I followed the steps below to list the hidden file and modified it.

- First, I typed in ``ls -la`` to list all files, including hidden files, and their permissions. Where ``-la`` displays all files and their permission including hidden files. All files that begin with ``.`` before their names, don't normally appear when you use ``ls``.

![All files including hidden files](https://github.com/user-attachments/assets/0befe1fd-967d-428d-a60a-68638d8fee03)

- As you can see in the above screenshot, the permission is set as ``rw--w----``. I then proceeded to modify the permission based on the appropriate permission using ``chmod``
- I typed ``chmod u-w,g-w+r .project_x.txt`` and clicked on Enter
- Lastly, I typed ``ls -la`` to view the modified permissions which was set as ``r--r-----`` allowing both the user and the group to only read the file.
### Step 4: Change Directory Permissions
The files and directories in the projects directory belong to the ``researcher2`` user. ``Only researcher2`` should be allowed to access the drafts directory and its contents. Here are the steps I followed to modify these permissions.

- First I typed in ``ls -l`` to reveal all permissions and the permissions were set as ``rwx--x---``
- I then modified it by typing ``chmod g-x drafts`` to remove the execute permission from the group and pressed Enter.
- Lastly, I typed ``ls -l`` to view the modified and the result was ``rwx------`` allowing users to read, write, and modify the directory.
