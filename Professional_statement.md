# Cybersecurity-Portfolio
## Professional Statement
 As a cybersecurity professional, I protect organizations from evolving cyber threats while upholding integrity and compliance with legal standards. With strong analytical and problem-solving skills, I specialize in security monitoring, threat analysis, and incident response. My expertise includes identifying vulnerabilities, implementing security controls, and educating stakeholders on cyber risks. I am proficient in leveraging security tools such as SIEMs, SQL, Python, IDS/IPS, and firewalls to detect and mitigate threats effectively. Passionate about continuous learning, I stay updated on emerging attack vectors and best practices to enhance security resilience.
## Introduction to Linux (Linux Commands to Manage Files)
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
- I typed ``chmod u-w,g-w,g+r .project_x.txt`` and clicked on Enter
- Lastly, I typed ``ls -la`` to view the modified permissions which was set as ``r--r-----`` allowing both the user and the group to only read the file.
### Step 4: Change Directory Permissions
The files and directories in the projects directory belong to the ``researcher2`` user. ``Only researcher2`` should be allowed to access the drafts directory and its contents. Here are the steps I followed to modify these permissions.

- First I typed in ``ls -l`` to reveal all permissions and the permissions were set as ``rwx--x---``
- I then modified it by typing ``chmod g-x drafts`` to remove the execute permission from the group and pressed Enter.
- Lastly, I typed ``ls -l`` to view the modified and the result was ``rwx------`` allowing users to read, write, and modify the directory.

## Summary
This project describes how to identify and manage files using Linux commands. Also, it shows what permissions are and how to list those permissions including those hidden permissions. Lastly, permissions are modified appropriately for authorized users.
## Introduction to SQL (Apply Filters to SQL Queries)
My job in my organization involves investigating security issues to help keep the system secure. My task is to examine the organization's data to retrieve records from different datasets and investigate potential security issues. Below are the steps I followed:
### Task 1. Retrieve after-hours failed login attempts
I discovered a potential security issue that occurred after business hours, and I needed to filter out the information querying the ``log_in_attempt_`` table to find out all unsuccessful login attempts after business hours.

![Filtering using AND OR](https://github.com/user-attachments/assets/8e451b97-4cd7-4231-aac2-60ef6faa55c9)

The first line shows that I selected all columns from the ``log_in_attempt`` using the SQL ``SELECT`` query and the second line shows ``FROM`` which table it should return the output. Also, for me to know the number of unsuccessful login attempts, I added ``18:00`` which was after business hours. This returned the list of failed login attempts that were made after 6 PM.
### Task 2. Retrieve login attempts on specific dates
A suspicious event occurred on 2022-05-09. To investigate this event, I want to review all login attempts that occurred on this day and the day before. I'll Use filters in SQL to create a query that identifies all login attempts that occurred on 2022-05-09 or 2022-05-08. 

![LOGIN DATES](https://github.com/user-attachments/assets/6503dbe5-7c34-44ed-aaaf-ca9f1b7fb582)

In the image above, I used ``SELECT *`` to select all columns ``FROM`` the ``log_in_attempts`` table which contains information on the dates when login attempts were made. I used ``OR`` query in between the strings of queries  ```WHERE login_date = '2022-05-09 OR login_date = '2022-05-08'`` to return all login attempts made between the two dates.
### Task 3. Retrieve login attempts outside of Mexico
There’s been suspicious activity with login attempts, but the team has determined that this activity didn't originate in Mexico. Now, I need to investigate login attempts that occurred outside of Mexico.

![MEXICO](https://github.com/user-attachments/assets/e793302d-91bb-4e20-8ea2-9c04bdebaf3a)

Looking at the image above, I used the ``%``, ``NOT`` and ``LIKE`` operators to match the pattern. After I selected all columns and from which table, I added the operators to return login attempts made outside of Mexico. 
### Task 4. Retrieve employees in Marketing
My team wants to perform security updates on specific employee machines in the Marketing department. I'm responsible for getting information on these employee machines and will need to query the ``employees`` table. 

![EMPLOYEES IN MARKETING](https://github.com/user-attachments/assets/6793354f-a68b-4a91-b17a-c8946e79a30b)

Here, to be able to select all columns and to include filters on the ``department`` and ``office`` columns, I used the ``AND`` and ``LIKE`` Operator to return all employees in the Marketing department.
### Task 5. Retrieve employees in Finance or Sales
The team now needs to perform a different security update on machines for employees in the Sales and Finance departments.

![FINANCE AND SALES](https://github.com/user-attachments/assets/5f4a9fb6-772f-4dda-bbba-1af37b7f9942)

To be able to create an SQL query that identifies all employees in the ``Sales`` and ``Finance`` departments, I used the ``OR`` operator to filter both tables out.
### Task 6. Retrieve all employees not in IT
The team needs to make one more update to employee machines. The employees who are in the Information Technology department already had this update, but employees in all other departments need it.

![NOT IT](https://github.com/user-attachments/assets/06c4b4da-63a8-4bc0-ae5c-7fe3d1165503)

The first line represents the query that selects all columns in the table and the next line shows from which table to select. I know that the team wants me not to include the ``IT department`` on the table. To do that, I included the ``NOT`` operator to filter the ``IT department`` out. 
## Conclusion
I have used different SQL queries to retrieve information from the employees' table to be able to examine different security issues. The first step was to be able to use the ``SELECT`` and ``FROM`` queries to understand which tables and columns I was filtering from. I also used operators like ``NOT``, ``OR``, and ``AND`` to be able to filter information in some columns which has helped me to identify potential security threats and ways to keep the system secure.
## Introduction to Python (Update a file through a Python algorithm)
### Project description
At my organization, access to restricted content is controlled with an allow list of IP addresses. The ``allow_list.txt`` file identifies these IP addresses. A separate remove list identifies IP addresses that should no longer have access to this content. I created an algorithm to automate updating the ``allow_list.txt`` file and removing these IP addresses that should no longer have access. 
### Open the file that contains the allow list
For the first part of the algorithm, I opened the ``allow_list.txt`` file. First, I assigned this file name as a string to the import_file variable:
``
#Assign 'import_file' to the name of the file

import_file = "allow_list.txt"
``
