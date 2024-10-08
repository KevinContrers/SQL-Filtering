# Cybersecurity Analysis: SQL Filters for Investigating Security Issues (Google Coursera Project)

## Scenario

As part of my hands-on training through the **Google Cybersecurity Professional Certificate**, I investigated potential security issues within an organization by analyzing login attempts and employee data using **SQL filters**. My task was to retrieve data from the **log_in_attempts** and **employees** tables, filtering records to identify security-related issues and refine permissions based on the results.

---

## Incident Analysis

During this project, I used SQL queries with filters to extract information on suspicious login attempts and employee access to sensitive systems. The following use cases outline how I applied different SQL operators such as **AND**, **OR**, **NOT**, and **LIKE** to investigate the data.

### 1. Failed After-Hours Login Attempts

To investigate failed login attempts that occurred after business hours (post 18:00), I created a query that filtered the **log_in_attempts** table.

| **SQL Query**              | **Description**                                                                 |
|----------------------------|---------------------------------------------------------------------------------|
| `SELECT * FROM log_in_attempts WHERE login_time > '18:00' AND success = FALSE;` | Filtered for all failed login attempts after 18:00.                       |

### 2. Login Attempts on Specific Dates

To investigate a suspicious event on May 9, 2022, and the day before, I used the **OR** operator to filter the login attempts.

| **SQL Query**              | **Description**                                                                 |
|----------------------------|---------------------------------------------------------------------------------|
| `SELECT * FROM log_in_attempts WHERE login_date = '2022-05-09' OR login_date = '2022-05-08';` | Retrieved login attempts from May 8th and 9th, 2022.                      |

### 3. Login Attempts Outside of Mexico

To investigate login attempts occurring outside of Mexico, I filtered the **log_in_attempts** table for any countries other than Mexico using the **NOT** and **LIKE** operators.

| **SQL Query**              | **Description**                                                                 |
|----------------------------|---------------------------------------------------------------------------------|
| `SELECT * FROM log_in_attempts WHERE country NOT LIKE 'MEX%';` | Filtered login attempts outside Mexico, considering variations like MEX and MEXICO. |

---

## Employee Machine Updates

Alongside investigating login attempts, I identified employees in specific departments to perform security updates on their computers. I used the **employees** table and various filters to retrieve necessary data.

### 1. Employees in Marketing Department (East Building)

To identify employees in the Marketing department located in the East building, I applied the **AND** operator in combination with **LIKE**.

| **SQL Query**              | **Description**                                                                 |
|----------------------------|---------------------------------------------------------------------------------|
| `SELECT * FROM employees WHERE department = 'Marketing' AND office LIKE 'East%';` | Retrieved employees from Marketing in the East building.                  |

### 2. Employees in Finance or Sales Departments

To filter employees in either the Finance or Sales departments, I used the **OR** operator.

| **SQL Query**              | **Description**                                                                 |
|----------------------------|---------------------------------------------------------------------------------|
| `SELECT * FROM employees WHERE department = 'Finance' OR department = 'Sales';` | Retrieved employees from either Finance or Sales departments.            |

### 3. Employees Not in IT Department

To filter out employees who are not in the IT department, I applied the **NOT** operator.

| **SQL Query**              | **Description**                                                                 |
|----------------------------|---------------------------------------------------------------------------------|
| `SELECT * FROM employees WHERE department NOT LIKE 'IT';` | Retrieved employees from all departments except IT.                        |

---

## Summary

This project involved the use of **SQL queries** with filters to investigate security issues by retrieving specific data on login attempts and employee machines. Through SQL, I was able to identify patterns of failed login attempts, isolate unauthorized access attempts, and prepare a strategy for updating the organization's systems based on department-specific requirements.

---

## Tools & Technologies Used

| **Tool/Technology**        | **Purpose**                                                      |
|----------------------------|------------------------------------------------------------------|
| **SQL**                    | Used to query the organization's database and retrieve specific records for investigation. |
| **log_in_attempts Table**   | Analyzed login attempts for potential security incidents.        |
| **employees Table**         | Retrieved employee information for security updates.             |

---

This project reinforced my ability to use **SQL** to investigate security-related data, and it showcased the value of structured queries in identifying potential threats and applying system-wide updates. It further expanded my knowledge in filtering datasets for cybersecurity purposes, ensuring more secure and effective system management.
