# SQL-Project-Job-Adverts 
## Questions and Answers

**Author**: Aytekin Can

**Email**: aytekincan92@gmail.com

**LinkedIn**: https://www.linkedin.com/in/aytekincan

A SQL analysis of cars sold on Carsonline and the prices of car models by year, the average price of each transmission, number of hybrid cars for each car make, manual-gearbox cars by each car year and customers information such as number of customers by each gender and age and what are the countries of these customers.

#### a. Write a query to display the job_id, job_title, salary_estimate_min, salary_estimate_max
#### b. Repeat your last query, only this time display only the job adverts where salary_estimate_max is less than 105,000
````sql
SELECT TOP 10 job_id, job_title, salary_estimate_min, salary_estimate_max
FROM jobs
WHERE REPLACE(salary_estimate_max,'K','') < 105
````
**Results:**
job_id|	job_title|	salary_estimate_min|	salary_estimate_max|
6|	Database Administrator II|	18K|	104K|
23|	Environmental Specialist|	10K|	103K|
40|	Graphic Designer|	98K|	103K|
62|	Human Resources Manager|	81K|	101K|
66|	Physical Therapy Assistant|	50K|	104K|
106|	Software Engineer IV|	44K|	101K|
110|	Technical Writer|	35K|	102K|
124|	Sales Associate	100K|	101K|
128|	Structural Engineer|	22K|	101K|
138|	Help Desk Operator|	91K|	102K|
