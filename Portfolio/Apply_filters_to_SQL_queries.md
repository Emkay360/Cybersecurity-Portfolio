## Project Description
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
