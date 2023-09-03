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



#### Which job adverts were removed after a single day ? :
````sql
SELECT job_id, job_title, published_date, removed_date
FROM jobs
WHERE DATEDIFF(DAY, published_date, removed_date) = 1
````
job_id|job_title|published_date|removed_date|
-------|--------|--------------|------------|	
264|Senior Editor|2020-01-19 03:28:44.000|2020-01-20 03:28:44.000|
560|Occupational Therapist|2016-06-20 18:54:55.000|2016-06-21|18:54:55.000|
723|Civil Engineer|2017-01-17 17:33:49.000|2017-01-18 17:33:49.000|
923|Quality Engineer|2017-05-21 02:45:17.000|2017-05-22 02:45:17.000|



#### Which job adverts were posted on the same day and month as the current date ?
````sql
SELECT job_id, job_title, published_date, removed_date
FROM jobs
WHERE DAY(published_date) = DAY(GETDATE())
AND   MONTH(published_date) = MONTH(GETDATE())
````
job_id|job_title|published_date|removed_date|
------|---------|--------------|------------|	
245|Occupational Therapist|2018-08-17 10:53:58.000|2018-10-16 10:53:58.000|
390|Programmer Analyst III|2017-08-17 15:24:13.000|2017-11-06 15:24:13.000|
393|Human Resources Manager|2017-08-17 09:25:56.000|2017-10-28 09:25:56.000|
397|Nuclear Power Engineer|2017-08-17 01:03:36.000|2017-09-07 01:03:36.000|

#### In a few job adverts, the value of published_date is greater than the removed_date,  those rows represent invalid data.
````sql
SELECT job_id, job_title, published_date, removed_date
FROM jobs 
WHERE published_date > removed_date
````

job_id|job_title|published_date|removed_date|
------|---------|--------------|------------|
410|Account Executive|2017-09-08 05:21:17.000|2016-09-29 05:21:17.000|
421|VP Product Management|2019-08-06 20:22:45.000|2017-08-30 20:22:45.000|
431|Electrical Engineer|2021-02-03 08:13:52.000|2018-05-13 08:13:52.000|
474|Software Consultant|2019-01-17 07:15:18.000|2010-03-10 07:15:18.000|

#### Take your previous report and instead of the NULL values:
#### a. Display the current date instead of NULL values in removed_date
#### b. Display the company_state instead of NULL values in headquarters_of_company
#### c. Display 'Not Available' instead of NULL values in company_name

````sql
SELECT job_id, job_title,

	ISNULL(removed_date, GETDATE()) AS 'removed_date',
	ISNULL(headquarters_of_company, state_of_company) AS 'headquarters_of_company',
	ISNULL(company_name,'Not Available') AS 'company_name'

FROM jobs

WHERE removed_date IS NULL OR
	  headquarters_of_company  IS NULL OR
	  company_market_value IS NULL
````

job_id|job_title|removed_date|headquarters_of_company|company_name|
--------|--------|-----------|-----------------------|------------|
3|Physical Therapy Assistant|2016-12-18 10:24:03.000|Colorado|Gabvine
61|NULL|2018-03-13 14:50:44.000|Colorado|Rhybox|
364|Nurse Practicioner|2020-12-06 18:14:59.000|Colorado|Mybuzz|
406|Human Resources Assistant I|2019-07-06 20:40:42.000|Florida|Tambee|
426|NULL|2016-12-15 01:10:32.000|Florida|Voonyx|
494|Desktop Support Technician|2019-09-03 04:45:52.000|Colorado|Katz|
501|Data Coordiator|2020-10-07 02:30:18.000|Colorado|Thoughtmix|
513|Health Coach I|2018-07-06 18:11:51.000|Florida|Voonix|
582|Physical Therapy Assistant	|2018-09-11 17:14:33.000|Florida|Skimia|
632|Geologist III|2023-08-17 11:04:49.587|Akron|Jetwire|

### Write a query to display the company_name, company_market_value, and a new column : company_market_value_rank, based on the following logic:

### For companies with market_value in the range of 0-300 provide the rank : 'low range'

### For companies with market_value in the range of 301-600 provide the rank : 'mid range'

### For companies with market_value in the range of 601-900 provide the rank : 'high range'

### For any other range provide the rank : 'other range'

````sql
SELECT job_title, company_name, company_size_min, company_size_max, 
         CASE WHEN REPLACE(company_size_max, ' Employees', '') <= 60 THEN 'Small Company'
         WHEN REPLACE(company_size_max, ' Employees', '') <=  120 THEN 'Medium Company'
         WHEN REPLACE(company_size_max, ' Employees', '') <=  180 THEN 'Large Company'
         ELSE 'Unknown'
         END AS 'company_size'
FROM  jobs

````
job_title|company_name|company_size_min|company_size_max|company_siz|
---------|------------|----------------|----------------|-----------|
Administrative Assistant II|Kwilith|40 Employees|68 Employees|Medium Company|
Software Engineer II|Photojam|50 Employees|85 Employees	Medium Company|
Physical Therapy Assistant|Gabvine|40 Employees|68 Employees|Medium Company|
Research Assistant I|Lajo|10 Employees|17 Employees|Small Company|
Assistant Professor|Avaveo|30 Employees|51 Employees|Small Company|
Database Administrator II|Brainverse|70 Employees|119 Employees|Medium Company|
Account Coordinator|Linklinks|60 Employees|102 Employees|Medium Company|
Associate Professor|Tazzy|20 Employees|34 Employees|Small Company|
Budget/Accounting Analyst IV|Wikizz|30 Employees|51 Employees|Small Company|
Database Administrator I|Linktype|50 Employees|85 Employees|Medium Company|






