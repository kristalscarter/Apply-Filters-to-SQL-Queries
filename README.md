<h1>Apply Filters to SQL Queries</h1>


<h2>Description</h2>
The following lab was completed to display the method in which SQL is used to filter queries. The following sample project shows how and why a Cybersecurity Analyst would complete this type of task. 
<br />

<h2>Project Background</h2>
The organization is striving to enhance the security of their system. The assigned responsibility entails ensuring the system's safety, conducting investigations into potential security issues, and making necessary updates to employee computers. The subsequent steps demonstrate the utilization of SQL with filters to carry out security-related tasks.
<br />

<h2>Languages and Utilities Used</h2>

- <b>MySQL</b> 
- <b>SQL</b>

<h2>Environments Used </h2>

- <b>Command-line Interface</b> 

<h2>Program walk-through:</h2>

<h2>Retrieve after hours failed login attempts:</h2>
A potential security incident took place outside of regular business hours (post 18:00). It is necessary to conduct an investigation into all failed login attempts that occurred during this time period. The subsequent code exemplifies the creation of a SQL query designed to filter and identify failed login attempts that transpired after business hours.
<br/>
<p align="center">
  <img src="https://imgur.com/fR30Ivk.png" height="80%" width="80%" alt="Apply Filters to SQL Query"/>

The provided screenshot consists of two parts: the query and a portion of the output. The query focuses on filtering failed login attempts that happened after 18:00. Initially, all data from the log_in_attempts table is selected. Subsequently, a WHERE clause with an AND operator is employed to narrow down the results to only include unsuccessful login attempts occurring after 18:00.

The first condition, login_time > '18:00', ensures that login attempts after 18:00 are included in the output. The second condition, success = FALSE, further filters the results to only display failed login attempts.
<br />
<br />
<h2>Retrieve login attempts on specific dates:</h2>
A suspicious event was identified on the date 2022-05-09. As part of the investigation, it is necessary to examine all login activity that transpired on 2022-05-09 and the preceding day. The subsequent code exemplifies the creation of a SQL query to filter and identify login attempts that occurred on the specified dates. <br/>
<p align="center">
  <img src="https://imgur.com/aEohJIu.png" height="80%" width="80%" alt="Apply Filters to SQL Query"/>

The provided screenshot consists of two parts: the query and a portion of the output. The query aims to retrieve all login attempts that transpired on either 2022-05-09 or 2022-05-08.

Initially, all data from the log_in_attempts table is selected. Subsequently, a WHERE clause with an OR operator is utilized to filter the results and display only login attempts that occurred on either 2022-05-09 or 2022-05-08.

The first condition, login_date = '2022-05-09', ensures that login attempts on 2022-05-09 are included in the output. Similarly, the second condition, login_date = '2022-05-08', filters for login attempts on 2022-05-08.
<br />
<br />
<h2>Retrieve login attempts outside of Mexico:</h2>
Based on the investigation conducted on the organization's login attempts data, there appears to be a concern regarding login attempts originating from locations outside of Mexico. It is recommended to further investigate these login attempts. The provided code demonstrates the creation of a SQL query to filter and identify login attempts that took place outside of Mexico.
<p align="center">
  <img src="https://imgur.com/nuhzFRD.png" height="80%" width="80%" alt="Apply Filters to SQL Query"/>

The screenshot provided contains two parts: the query and a segment of the output. The query aims to retrieve all login attempts that transpired in countries other than Mexico.

The process begins by selecting all data from the log_in_attempts table. Subsequently, a WHERE clause with the NOT operator is utilized to filter the results and exclude login attempts originating from Mexico. To achieve this, the LIKE operator is used, with the pattern 'MEX%' employed to match the country codes representing Mexico in the dataset, namely 'MEX' and 'MEXICO'. The percentage sign (%) is utilized in conjunction with LIKE to represent any number of unspecified characters.

As a result, the query returns login attempts that occurred in countries other than Mexico based on the applied filtering criteria.
<br />
<br />
<h2>Retrieve employees in Marketing:</h2>
The team aims to update the computers of specific employees working in the Marketing department. To accomplish this, it is necessary to gather information regarding the employee machines that require updating. The provided code exemplifies the creation of a SQL query designed to filter and identify employee machines belonging to employees in the Marketing department within the East building.
<p align="center">
  <img src="https://imgur.com/V4vHF4e.png" height="80%" width="80%" alt="Apply Filters to SQL Query"/>

The provided screenshot includes two parts: the query and a subset of the output. The query focuses on retrieving information about employees who belong to the Marketing department in the East building.

The query begins by selecting all data from the employees table. Next, a WHERE clause with the AND operator is employed to filter the results. The first condition, department = 'Marketing', ensures that only employees from the Marketing department are included. The second condition, office LIKE 'East%', uses the LIKE operator with the pattern 'East%' to match the office column entries representing the East building (e.g., East 1, East 2). 

Consequently, the query returns information about employees who meet both criteria: being part of the Marketing department and working in the East building.
<br />
<br />
<h2>Retrieve employees in Finance or Sales:</h2>
In addition to the Marketing department, the machines of employees in the Finance and Sales departments also require updating. As a different security update is necessary for these departments, it is crucial to gather information solely on employees belonging to Finance or Sales. The provided code showcases the creation of a SQL query designed to filter and identify employee machines specifically from the Finance or Sales departments.
<p align="center">
  <img src="https://imgur.com/sw9kEdo.png" height="80%" width="80%" alt="Apply Filters to SQL Query"/>

In the screenshot provided, the first part demonstrates your query, while the second part showcases a subset of the output. This query aims to retrieve information on employees in the Finance and Sales departments.

The query starts by selecting all data from the employees table. Next, a WHERE clause with the OR operator is used to filter the results. The reason for using OR instead of AND is to include all employees who belong to either the Finance or Sales department. The first condition, department = 'Finance', filters for employees in the Finance department, while the second condition, department = 'Sales', filters for employees in the Sales department.

As a result, the query returns all employees from the Finance and Sales departments based on the applied filtering criteria.
<br />
<br />
<h2>Retrieve all employees not in IT:</h2>
To perform an additional security update, the team aims to focus on employees outside of the Information Technology department. To proceed with the update, it is necessary to gather information on these employees. The following SQL query exemplifies the process of filtering for employee machines belonging to individuals who are not part of the Information Technology department.
<p align="center">
  <img src="https://imgur.com/e1QS3Co.png" height="80%" width="80%" alt="Apply Filters to SQL Query"/>

The provided screenshot consists of two parts: the query and a segment of the output. The query aims to retrieve all employees who are not part of the Information Technology department.

To achieve this, the query begins by selecting all data from the employees table. Subsequently, a WHERE clause with the NOT operator is utilized to filter the results and exclude employees belonging to the Information Technology department.

As a result, the query returns information about employees who are not part of the Information Technology department, based on the applied filtering criteria.
<br />
<br />
<h2>Summary:</h2>
Filters were implemented in SQL queries to retrieve specific information on login attempts and employee machines from two distinct tables: log_in_attempts and employees. The query filters utilized various operators such as AND, OR, and NOT to refine the results based on specific criteria for each task. The LIKE operator, in combination with the percentage sign (%) wildcard, was employed to filter for patterns in the data.


<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
