# Applying Filters in SQL Queries for security-related tasks

## Project Scenario 
My job is to make sure the organization's system is safe. I check for security risks, update computers and use SQL to filter for security-related tasks. 

## Retrieve after-hours failed login attempts

There was a security incident that needs to be investigated. Specifically, we are looking at failed login attempts after usual office hours (18:00). 

Below is how I used SQL to filter out the database for failed login attempts after 18:00. 


<img width="709" alt="AD_4nXc3L2HLQ8ovettktTsMrQhTVSlolQA1ImBAXbJeiVGBuRugeKeUQrIiQRsLDLYiKdbYfVBNhiuZwxrRASR1-5lF3qk8WJ1H-_yDKRlowyRkqxla38abZn3K" src="https://github.com/SteveSunny46/Applying-Filters-in-SQL-Queries-for-security-related-tasks/assets/171859383/1aeecc41-45c2-4897-ac32-d930bf2a45c4">


The second line shows the beginning of my query and the next is the portion of the output. 

- First, I started by selecting all data from the log_in_attempts table.

-   Then, I used a WHERE clause with an AND operator to filter my results to output only login attempts that occurred after 18:00 and were unsuccessful. The first condition is login_time > '18:00', which filters for the login attempts that occurred after 18:00. The second condition is success = FALSE in which the binary input would be 0, which filters for the failed login attempts.

  

## Retrieve login attempts on specific dates

A suspicious event occurred on 2022-05-09. The login_date will help us investigate the filter for logins that occurred on this date and the day before. The following is how I used SQL to filter out login attempts on those two specific dates.


<img width="709" alt="AD_4nXeWIZbFlce7El6FnAb1-8yHnc9neCbvZwAugJJRHw-NVNfPOEVWpPPN1bW6r6ve-IEJOZstEDuA-VNw-q1IGi8gQXHkdgTrC2sxFOhtSQAO-UEtwM-XB9ic" src="https://github.com/SteveSunny46/Applying-Filters-in-SQL-Queries-for-security-related-tasks/assets/171859383/7749f000-2835-4941-8dc3-0e1235aa299e">

 This query returns all login attempts that occurred on 2022-05-09 or 2022-05-08. 

- First, I started by selecting all data from the log_in_attempts table.
  
- Then, I used a WHERE clause with an OR operator to filter my results to output only login attempts that occurred on either 2022-05-09 or 2022-05-08. The first condition is login_date = '2022-05-09', which filters for logins on 2022-05-09. The second condition is login_date = '2022-05-08', which filters for logins on 2022-05-08.

## Retrieve login attempts outside of Mexico

After further investigation, there may be an issue with login attempts outside of Mexico. These login attempts are investigated in the following screenshot.


<img width="709" alt="AD_4nXfQwOKmlIyn3fjLC8un3oVB8RQN8P-8P5ThE6-ubG1bA8AjAkZj1CwKwUZkk_VEcIPm1PsUy_TiPXUZ8N4HxNpT55vD_fMwDGIquKmN3vkKhnDbT4MtWclj" src="https://github.com/SteveSunny46/Applying-Filters-in-SQL-Queries-for-security-related-tasks/assets/171859383/7989d435-a606-4d39-8df1-35c323f3dbb7">

This query returns all login attempts that occurred in countries other than Mexico.

- First, I started by selecting all data from the log_in_attempts table.

- Then, I used a WHERE clause with NOT to filter for countries other than Mexico. I used LIKE with mex% as the pattern to match because the dataset represents Mexico as MEX and MEXICO. The percentage sign (%) represents any number of unspecified characters when used with LIKE.

## Retrieve employees in Marketing

The team is updating employee computers and it needs to gather information on employees in the marketing department in all the east offices.  Below is a screenshot of the query used to filter for marketing employees located in east buildings. 


<img width="709" alt="Marketing" src="https://github.com/SteveSunny46/Applying-Filters-in-SQL-Queries-for-security-related-tasks/assets/171859383/3a93ce5a-da6e-4262-9192-82cd46caad9f">

This query returns all employees in the Marketing department in the East building. 

- First, I started by selecting all data from the employee's table.

- Then, I used a WHERE clause with AND to filter for employees who work in the Marketing department and in the East building. I used LIKE with east% as the pattern to match because the data in the office column represents the East building with the specific office number.

- The first condition is the office LIKE 'East%' portion, which filters for employees in the East building. The second condition used is to filter the 'Marketing' portion, this filters for employees in the Marketing department.

## Retrieve employees in Finance or Sales

Employees in the Finance and Sales department also need their computers updated. To gather information on employees from just these two departments I used the following query used in the screenshot below. 

<img width="709" alt="AD_4nXfn1pOb_MABcAIsLOJvMfswVcoSwz8Zoz1qIwgom4yjyOvmtEvRPRLT9DJheJJU3jiT-iDC1-Wj4muU7Co8urMm_PDMS6z0W5xujXGSWuYT6Z6GrGuBRbHr" src="https://github.com/SteveSunny46/Applying-Filters-in-SQL-Queries-for-security-related-tasks/assets/171859383/96efe246-2dec-4448-aa38-89f1bae21981">

This query returns all employees in the Finance and Sales departments. 

- First, I started by selecting all data from the employee's table.
  
- Next, I used a WHERE clause with OR to filter for employees who are in the Finance and Sales departments. I used the OR operator instead of AND because I want all employees who are in either department.

- The first condition is department = 'Finance', which filters for employees from the Finance department. The second condition is department = 'Sales', which filters for employees from the Sales department.

## Retrieve all employees not in IT

The team wants to make an update on employees who are not in the Information Technology department, to do this I used the following SQL query to filter out the employees who are not in the Information Technology department. 

<img width="709" alt="AD_4nXdxIdNkEP8ermwiw3zNoeOHynXII6k6i2XzAuorjT_uof23cZc4nZNcqca64W5zqho80CXmTo_ERs2y-6ueitAa92xcMd1wWVvcM7AX8FGsGH4ZKyg5h_gx" src="https://github.com/SteveSunny46/Applying-Filters-in-SQL-Queries-for-security-related-tasks/assets/171859383/01691dae-802f-44f6-904d-01e8c079b3cd">

The query returns all the employees who are not in the Information Technology department.

- First, I started by selecting all data from the employee's table.

- Then, I used a WHERE clause with NOT to filter for employees not in this department allowing me to efficently filter out just the Information Technology department. 


