# SQL-Project-Job-Adverts 
## Questions and Answers

**Author**: Aytekin Can

**Email**: aytekincan92@gmail.com

**LinkedIn**: https://www.linkedin.com/in/aytekincan

A SQL analysis of random made workers.

#### a. Write a query to display the job_id, job_title, salary_estimate_min, salary_estimate_max
#### b. Repeat your last query, only this time display only the job adverts where salary_estimate_max is less than 105,000
````sql
SELECT TOP 10 job_id, job_title, salary_estimate_min, salary_estimate_max
FROM jobs
WHERE REPLACE(salary_estimate_max,'K','') < 105
````
**Results:**
job_id|	job_title|salary_estimate_min|	salary_estimate_max|
--------|------------|-------------------------|-------------------------|
6|	Database Administrator II|	18K|	104K|
23|	Environmental Specialist|	10K|	103K|
40|	Graphic Designer|	98K|	103K|
62|	Human Resources Manager|	81K|	101K|
66|	Physical Therapy Assistant|	50K|	104K|
106|	Software Engineer IV|	44K|	101K|
110|	Technical Writer|	35K|	102K|
124|	Sales Associate| 100K|	101K|
128|	Structural Engineer|	22K|	101K|
138|	Help Desk Operator|	91K|	102K|

#### Write a query to display the company_name, company_rank, company_size_min, and company_size_max
for companies with more than 60 employees and less than 120 employees
````sql
SELECT DISTINCT company_name, company_rank, company_size_min, company_size_max
FROM jobs
WHERE REPLACE(company_size_min, ' Employees', '') > 60 AND 
      REPLACE(company_size_max, ' Employees', '') < 120,
````
**Results:**
company_name|company_rank|company_size_min|company_size_max|
--------------------|------------------|-----------------------|------------------------|
Babbleblab|8|70 Employees|119 Employees|
Babbleopia|8|70 Employees|119 Employees|
Blognation|8|70 Employees|119 Employees|
Brainverse|8|70 Employees|119 Employees|
Brightbean|8|	70 Employees|119 Employees|
Browseblab|8|	70 Employees|119 Employees|
Browsetype|8|	70 Employees|119 Employees|
Bubbletube|8|	70 Employees|119 Employees|
Divanoodle|8|	70 Employees|119 Employees|
Feednation|8|70 Employees|	119 Employees|
Flashpoint|8|	70 Employees|	119 Employees|
Jabberbean|8|	70 Employees|	119 Employees|
Linkbridge|8|	70 Employees|	119 Employees|
Photospace|8|	70 Employees|	119 Employees|
Shuffletag|8|	70 Employees|	119 Employees|
Thoughtmix|8|	70 Employees|	119 Employees|
Topicshots|8|70 Employees|119 Employees|
Topicstorm|8|	70 Employees|	119 Employees|
Zoomlounge|8|70 Employees|	119 Employees|


#### Write a query to display the :
#### a. job_id
#### b. job_title in uppercase
#### c. company_name in lowercase
````sql
SELECT TOP 10 job_id, UPPER(job_title) AS 'upper_jobtitle', LOWER(company_name) AS 'lower_companyname'
FROM jobs
````
**Results:**
job_id|	upper_jobtitle|	lower_companyname|	
-------|-------------------|----------------------------|	
1|ADMİNİSTRATİVE ASSİSTANT II|kwilith|	
2|SOFTWARE ENGİNEER II|photojam|	
3|PHYSİCAL THERAPY ASSİSTANT|gabvine|	
4|RESEARCH ASSİSTANT I|lajo|	
5|ASSİSTANT PROFESSOR|avaveo|	
6|DATABASE ADMİNİSTRATOR II|brainverse|	
7|ACCOUNT COORDİNATOR|linklinks|	
8|ASSOCİATE PROFESSOR|tazzy|	
9|BUDGET/ACCOUNTİNG ANALYST IV|wikizz|	
10|DATABASE ADMİNİSTRATOR I|linktype|	


#### Write a query to display the job_id, job_title, published_date, and removed_date for all jobs that were published on 2016
````sql
SELECT TOP 15 job_id, job_title, published_date, removed_date 
FROM jobs
WHERE YEAR(published_date) = 2016
````
**Results:**	

job_id|job_title|published_date|removed_date|
------|---------|--------------|------------|	
3|Physical Therapy Assistant|2016-10-14 10:24:03.000|2016-12-18 10:24:03.000|
4|Research Assistant I|2016-11-14 04:18:12.000|2017-01-21 04:18:12.000|
8|Associate Professor|2016-05-03 02:56:17.000|2016-07-03 02:56:17.000|
12|NULL|2016-10-13 17:47:31.000|2016-12-14 17:47:31.000|
17|Systems Administrator III|2016-03-10 15:56:12.000|2016-05-05 15:56:12.000|
20|Account Representative III|2016-10-25 16:43:40.000|2017-02-02 16:43:40.000|
26|Food Chemist|2016-08-29 07:19:20.000|2016-12-03 07:19:20.000|
35|Help Desk Technician|2016-04-11 08:05:27.000|2016-05-03 08:05:27.000|
53|Associate Professor|2016-03-23 |11:40:52.000|2016-06-02 11:40:52.000|
66|Physical Therapy Assistant|2016-08-20 00:59:38.000|2016-10-25 00:59:38.000|
73|Senior Sales Associate|2016-06-04 21:00:42.000|2016-08-17 21:00:42.000|
76|Sales Associate|2016-09-05 13:02:45.000|2016-10-31 13:02:45.000|
77|Programmer Analyst IV|2016-08-24 08:44:17.000|2016-10-26 08:44:17.000|
86|Database Administrator II|2016-02-11 12:49:37.000|2016-03-07 12:49:37.000|
87|Design Engineer|2016-05-24 08:32:27.000|2016-08-11 08:32:27.000|
