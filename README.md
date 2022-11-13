PayrollManagement

Team members: Margi Praful Adesara (NUID – 002792152) Sanhita Sawant (NUID – 002786796)

Github Id’s: MargiAdesara & sanhita54742

ReadMe Document:

The "Payroll Management System" is intended to automate the current manual system using computer software, meeting their needs and enabling for the storage of their vital information and data for a longer period of time with simple access and manipulation. The necessary software is readily available and simple to use. Without receiving duplicate entries, this web application can maintain and view records. The project outlines how to organize user data for optimal efficiency and to provide better services.
Payroll consists of the process by which a business pays its employees for work performed during a specific period. A payroll system allows businesses to follow a set series of processes in order to make timely, correct payments in compliance with government regulations. The payroll process typically includes calculating employee pay, recording payroll transactions. A company must have in place a timekeeping system that accurately reflects the hours and number of days put in by employees as well as the regular salary payments for exempt workers. Companies also must withhold Social Security and Medicare contributions from employees' salary and pay a matching amount. 

 
 

SQL Statements for the conceptual model: 

User Table: 

CREATE TABLE `User` ( 

 ‘User_Id’  INT, 

  ‘UserName’ VARCHAR (100), 

  ‘Password’ VARCHAR(100), 

  ‘Email_Id’ VARCHAR(100), 

  ‘UserType’ VARCHAR(50), 

  PRIMARY KEY  (‘User_Id’) 

); 

 
Project Table: 

CREATE TABLE `User` ( 

‘Project_Id’  INT, 

 ‘ProjectName’ VARCHAR (100), 

  PRIMARY KEY  (‘Project_Id’) 

); 

 

PayGrade Table: 

CREATE TABLE `PayGrade` ( 

‘PayGrade_Id’ INT, 

‘PayGrade_Basic’ INT, 

‘PayGrade_Bonus’ INT, 

‘PayGrade_Pf’ INT, 

‘PayGrade_Tax’ INT, 

PRIMARY KEY  (‘PayGrade_Id’) 

); 

 

Employee Table: 

CREATE TABLE `Employee` ( 

‘Emp_Id’ INT, 

‘Project_Id’ INT, 

‘Emp_name’ VARCHAR(100), 

‘Emp_Dob’ DATE, 

‘Emp_Doj’ DATE, 

‘Emp_Mobile’ BIGINT, 

‘Emp_Email’ VARCHAR(100), 

PRIMARY KEY  (‘Emp_Id’) 

); 

 

Salary Table: 

CREATE TABLE `Employee` ( 

‘Transaction_Id’ INT, 

‘Emp_Id’ INT, 

‘Emp_Salary_Month’ VARCHAR(100), 

‘Emp_Salary_Year’ VARCHAR(100), 

‘Imp_Department_Id’ INT, 

‘Emp_Basic’ BIGINT, 

‘Emp_Tax’ INT, 

PRIMARY KEY  (‘Transaction_Id’) 

); 

 

Tweets Table: 

CREATE TABLE `Tweets` ( 

Tweet_Id’ INT, 

‘TweetUser’ VARCHAR(100), 

‘TweetUrl’ VARCHAR(100), 

‘TweetText’ TEXT,  

‘TweetTime’ DATETIME, 

‘TweetLikes’ INT, 

‘TweetRetweet’ INT, 

‘ProfileImageUrl’ TEXT, 

‘TweetLocation’ TEXT, 

PRIMARY KEY  (‘Tweet_Id’) 

); 

 

Tweet_URL Table: 

CREATE TABLE `Tweet_URL` ( 

‘TweetURL_Id’ INT, 

‘TweetUrl’ VARCHAR(100), 

‘Tweet_Id’ INT,  

PRIMARY KEY  ('TweetURL_Id') 

); 

 

 

Constraint for Tweet_URL Table: 

ALTER TABLE `Tweet_URL` 

ADD CONSTRAINT `TweetsURL_fk1` FOREIGN KEY (‘Tweet_Id’) 

REFERENCES Tweets(‘Tweet_Id’); 

 

 

 

Constraint for Tweet_URL Table: 

ALTER TABLE `Tweet_URL’ 

ADD CONSTRAINT `TweetsURL_fk1’ FOREIGN KEY (‘Tweet_Id’) 

REFERENCES Tweets(‘Tweet_Id’); 

 

Constraint for Employee Table: 

ALTER TABLE `Employee’ 

ADD CONSTRAINT `EmployeeID_fk1’ FOREIGN KEY (‘Project_Id’) 

REFERENCES Project(‘Project_Id’); 

 

Constraint for Salary Table: 

ALTER TABLE `Salary’ 

ADD CONSTRAINT `EmployeeID_fk1’ FOREIGN KEY (‘Emp_Id’) 

REFERENCES Employee(‘Emp_Id’); 
