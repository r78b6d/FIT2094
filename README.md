java c
FIT2094 Databases - Assignment 2
Creating, Populating and Manipulating Databases - Paris Arrow Transit (PAT)
Purpose
Students will be asked to implement, via SQL, a small database in the Oracle RDBMS from a provided logical model case study, followed by the insert of appropriate data to the created tables. Once populated the database will be used to carry out specified DML commands and make specified changes to the database structure via SQL. Students will then use SQL and NoSQL to write queries to produce specified output. This task covers learning outcomes:
1. Apply the theories of the relational database model.
3. Implement a relational database based on a sound database design.
4. Manage data that meets user requirements, including queries and transactions.
5. Contrast the differences between non-relational database models and the relational database model.
Your task
This is an open book, individual task. The final output for this task will be a set of tables and data implemented in the Oracle RDBMS. In addition students will create a set of relational (Oracle) and non relational (MongoDB) queries which meet the user requirements.
Value
40% of your total marks for the unit
Due Date
Wednesday, 30th October 2024, 4:30 PM
(note: staff support is unavailable after business hours)
Submission
● Via Moodle Assignment Submission
● FIT GitLab check ins will be used to assess history of development
Assessment Criteria
● Application of relational database principles.
● Handling of transactions and the setting of appropriate transaction boundaries.
● Application of SQL statements and constructs to create and alter tables including the required constraints and column comments, populate tables, modify existing data in tables, and modify the "live" database structure to meet the expressed requirements (including appropriate use of constraints).
● Application of SQL select statements to produce outputs that meet user requirements.
● Mapping of relational database data into non relational database data structure.
● Application of MongoDB operations to produce outputs that meet user requirements.
INSTRUCTIONS
Your task for this assignment is to design a model for Paris Arrow Transit (PAT). Paris Arrow Transit is a private company subcontracted by the Olympic Federation to transport officials during the Olympic competition. The company realises that it needs a completely new computerised system to more efficiently manage and record its services during the Games. You have been asked to develop a database system that can meet PAT's needs, which are detailed below.
PAT owns a fleet of vehicles. Each vehicle is identified by its 17-character vehicle identification number (VIN), the company also records the registration plate (7 characters such as AB126FD), the make, such as Peugeot, the current odometer reading and the number of passengers which the vehicle can transport.
206 National Olympic Committee's (NOC) will compete at the Paris Games - each represents a particular country or region of the world. For each country/region, an identifying IOC code is recorded as well as the name of the country/region and its population. Each NOC will enter a team into the competition. The PAT system must track all officials who are part of these teams since they are the ones who will need to book official vehicles. One member of each NOC team is designated as the Chef De Mission (the team manager). PAT will record the official's Olympic ID and name for each official. The system records the manager (Chef De Mission) for each official. The Chef De Missions is listed as an official but has no manager since they are the team manager.
An official will book a trip with PAT to transport members of their team between various locations (these to/from locations will be further examined in Assignment 1 Logical - they should be omitted for now). A trip only involves a single vehicle. An official may use PAT's services multiple times (even during a single day); the only limiting factor is whether a suitable vehicle and driver is available at the date and time they wish to book travel. The vehicle is booked in the name of the official making the booking; the details of the actual passengers do not need to be recorded. The official booking the trip will also indicate the preferred language to be spoken during the trip so that the travellers can be understood by the driver and vice versa. Only a single preferred language for the trip will be indicated/recorded. The intended pick-up date and time and the projected drop-off date and time are recorded for each booked trip. In addition, PAT records the number of passengers needing transport for each booked trip.
PAT vehicles are driven by the company's drivers. Each driver is assigned a unique driver ID. The driver's name (given and family), licence number (18 characters in length), date of birth and the level of security clearance granted to the driver are recorded. Due to issues/problems that may arise, a driver may need to be suspended while a particular matter is investigated; while suspended a driver cannot drive any PAT vehicle - the system must be able to flag this. Driver security clearances are set at either F to represent Full or R to represent Restricted; the default should be R. Only a single driver  drives for a particular booked trip.
PAT records the languages that a driver speaks – some drivers speak several languages. To record languages, PAT will use ISO639-1 two-character language codes, for example, EN as English and ZH as Chinese – PAT records the ISO639-1 code and the name of the language.
Based on these requirements, a data model has been created for PAT: 
The schema/insert file for creating this model (pat_initialSchemaInsert.sql) is available in the archive  ass2_student.zip. This file partially creates the Pets First tables and populates several of them (those shown in purple on the supplied model). Please read this schema carefully and be sure you understand the various data requirements.
IMPORTANT points for you to observe when completing this assignment are:
1.   The ass2-student.zip archive also contains seven script. files to code your answers in. You
MUST ensure these files are regularly pushed to the GitLab server so that a clear
development history is available for the marker to verify your work (a minimum of
fourteen pushes are required - 2 pushes per file). In each file, you must fill in the header
details with your name and student ID before beginning work. Your SQL script. files must not include any SPOOL or ECHO commands. Although you might include such commands when testing your work, they must be removed before submission (a -10 mark grade penalty will    be applied if your documents contain spool or echo commands).
2.  You are free to make assumptions if needed. However, your assumptions must align with the details here and in the Ed Assignment 2 forum and must be clearly documented (see the required submission files).
3.  Views must not be used to arrive at any solutions for the tasks you must complete as part of this assessment.
4.  When handling dates with SQL, the default date format must not be assumed; you must use the TO_DATE and TO_CHAR functions where appropriate.
5.  ANSI joins must be used where the joining of tables is required.
6.   In completing the following tasks, you must design your test data so that you always get output for the queries specified below - this may require you to add further data as you move through completing the required tasks. Such extra data MUST be added as part of Task 2 (i.e. as part of your test data load). Queries that are correct but do not produce any output (“no rows selected” message) using your test data will lose 50% of the marks allocated. So, you should carefully check your test data and ensure it thoroughly validates  your SQL queries.
Steps for working on Assignment 2
1. Download the Assignment 2 Required Files zip archive (ass2-student.zip) from Moodle.
2. Extract the zip archive and place the contained files in your local repository in the folder: /Assignments/Ass2
Do not add the zip archive to your local repo.
3. Examine the extracted files, i.e. read carefully through them and ensure you understand their content.
4.  In each supplied script, fill in the header details with your name and student ID. Then, add, commit and push them to the FITGit Lab server.
5. Run pat_initialSchemaInsert.sql from the supplied zip archive to set up the initial state of the database.
6. Write your answer for each task in its respective file (e.g. write your answer for task 1 in T1-pat-schema.sql and so on).
7. Save, add, commit and push the file/s regularly while working on the assignment.
8. Finally, when you have completed all tasks, separately run each SQL or MongoDB as a script (not as individual statements) and ensure there are no errors. Upload all required files from your local repository to Moodle. Check that the files you have uploaded are the correct files (download them from Moodle into a temporary folder and check they are correct). After you are sure they are correct, submit your assignment.
************************************************************************************************************For all assignment tasks, your final script. must run as a script. without errors except for SQL  errors generated by the DROP TABLE/DROP SEQUENCE statements. Any task's script that  runs with an error will receive a maximum grade of half of the task's available marks -1. For example, if your task 1 script. runs with an error, regardless of the code contained, your maximum   grade will be 15/2 => 7.5 - 1 = 6.5 marks. This will be applied even if the error is simply a forgotten semicolon. Thus, please carefully check that your final scripts for all tasks run without error.
In arriving at your solutions for Assignment 2 you are ONLY permitted to use the SQL/NoSQL structures and syntax which have been covered within this unit:
●   Topic 6 Workshop and Applied 7 - Creating  Populating the Database
●   Topic 7 Workshop and Applied 8 - Insert, Update, Delete (DML) and Transaction Management
●   Topic 8 Workshop and Applied 9 - SQL Part I - Basic
●   Topic 9 Workshop and Applied 10 - SQL Part II- Intermediate
●   Topic 10 Workshop and Applied 11 - SQL Part III - Advanced
●   Topic 11 Workshop and Applied 12 - Non-Relational Database
As detailed above, SQL/NoSQL syntax and commands outside of the covered work will NOT be accepted/marked.
Views must not be used in completing these tasks.
You must also keep up to date with the Ed Assignment 2 forum where further clarifications may be posted. Please ensure you do not publicly post anything that includes your reasoning, logic, or any part of your work to this forum; doing so violates Monash plagiarism/collusion rules and has significant academic penalties. Attend a consultation session or use a private Ed post to raise such questions.
************************************************************************************************************
GIT STORAGE
Your work for these tasks MUST be saved in your  individual local working directory (repo) in the Assignment 2 folder and regularly pushed to the FIT GitLab server to build a clear history of the development of your approach. A minimum of fourteen pushes to the FIT Git Lab server is required (2 pushes per solution script). Please note that fourteen pushes are a minimum; we expect significantly more in practice. All commits must include a meani代 写FIT2094 Databases - Assignment 2 Creating, Populating and Manipulating Databases - Paris Arrow TransitR
代做程序编程语言ngful commit message that clearly    describes what the particular commit is about and must be correctly assigned to your valid GitLab author.
You must regularly check that your pushes have been successful by logging in to the FIT Git Lab server's web interface; you must not simply assume they are working. Before submission via Moodle, you must log in to the Git Lab server's web interface and ensure your submission files are present and their names are unchanged.
************************************************************************************************************
Assignment Tasks
TASK 1: DDL [15 mks]
ENSURE your ID and name are shown at the top of any file you submit.
For this task, you must add to T1-pat-schema.sql the CREATE TABLE and CONSTRAINT definitions, which are missing from the supplied partial schema script, in the positions indicated by the script's comments.  The table below details the attributes' meaning in the missing three tables. You MUST use exactly the same relation and attribute names shown in the data model above to name the tables and attributes you add. The attributes must be in the same order as shown in the model. These new DDL commands must be hand-coded, not generated in any manner (generated code will not be marked).
To test your code, you must first run the provided script. pat_initialSchemaInsert.sql to create the other required tables. pat_initialSchemaInsert.sql contains the drop commands for all tables in this model at the head of the file. If you have problems with task 1 simply rerun pat_initialSchemaInsert.sql, which will cause all tables to be dropped and correct the issues in your script. DO NOT add drop table statements to T1-pat-schema.sql
TASK 2: INSERT [20 mks]Before proceeding with Task 2, you must ensure you have run the file pat_initialSchemaInsert.sql  (which must not be edited in any way) followed by the extra definitions that you added in Task 1 above (T1-pat-schema.sql).
Load the VEHICLE, OFFICIAL and TRIP tables with your own test data using the supplied T2-pat-insert.sql script. file. Write SQL commands that will insert as a minimum (i.e. you may and should insert more) the following sample data:
(i)      10 VEHICLE entries
●    Include at least three vehicle models 
(ii)      10 OFFICIAL entries
●    Include at least four IOC Countries/Regions
(iii)      20 TRIP entries
●    Include at least five vehicles used in more than one trip
●    Include at least five officials booked more than one trip
●    Include at least five drivers
●    Include at least five languages
●    Include at least two parallel trips (i.e. trips that have the same intended pick-up/drop-off date times and the same pickup/drop-off locations)
In adding this data, you must ensure that the test data thoroughly tests the model as supplied to ensure your schema is correct (you are not required to submit or code fail tests; all insert statements must execute correctly).
Your inserted data must conform. to the following rules:
1.   Treat all the data you add as a single transaction since you are setting up the initial test state for the database.
2.   The primary key values for this data should be hardcoded values (i.e. NOT make use of
sequences). If the primary key attribute’s datatype is number, it must consist of values below 100.
3.   Trip dates used must be chosen between the 20th July 2024 and 15th August 2024.
4.   The data added must be sensible (e.g., the drop-off date should be after the pick-up date, the vehicle must accommodate the requested number of passengers, etc.).
For this task ONLY, Task 2, you may manually look up and include values for the loaded tables/data directly where required. However, you can still use SQL to get any non-key values if you wish. In carrying out Task 2, you must not modify any data or add any further data to  the tables populated by the pat_initialSchemaInsert.sql script. Design your test data to get output for the SQL scripts/queries specified below - this may require you to add further data as you complete the required tasks.
TASK 3: DML [20 mks]
Your answers for this task must be placed in the SQL file T3-pat-dml.sql For this and all subsequent Tasks, you are NOT permitted to:
●  manually lookup a value in the database, obtain its primary key, or manually obtain the highest/lowest value in a column,
●  manually calculate values external to the database, e.g. on a calculator and then use such    values in your answers. Any necessary calculations must be carried out as part of your SQL code or
●  assume any particular contents in the database - rows in a table are potentially in a constant state of change
Your answers must recognise that you are dealing with only a very small sample snapshot of a multiuser database; as such, you must operate on the basis that there will be more data in all of the database tables than you currently have access to. Thus, data will be in a constant state of change. Your answers must work regardless of the extra quantity of this extra "real" data and the fact that multiple users will operate in the tables simultaneously. You must consider this   aspect when writing SQL statements.For any following SQL tasks, your SQL must correctly manage transactions and use sequences to generate new primary keys for numeric primary key values (a new primary key value cannot   be hardcoded as a number or value).
You must ONLY use the data provided in the questions' text.
For Task 3, you must complete the following sub-tasks in the same order they are listed. Where you have been supplied with a string in italics, such as La Beaujoire Stadium, you may search in the database using the string as listed. Where a particular case for a word is provided, you must only use that case (same spacing, case, etc) in your SQL code. When a name is supplied, you may break the name into first name and last name. For example, James SMITH can be split into James and
SMITH; again, note that the case must be maintained as it was supplied. Failure to adhere to these requirements, such as changing the case of a provided string, will result in a grade penalty.
(a) Oracle sequences will be implemented in the database to insert records for the OFFICIAL and TRIP tables.
Provide the CREATE SEQUENCE statements to create sequences that could be used to provide primary key values for the OFFICIAL and TRIP tables. These sequences must start at 100 and increment by 10. Immediately before the create sequence commands, place appropriate DROP SEQUENCE commands so that the sequences will be dropped before being created if they exist. Please note that these are the ONLY sequences that can be    introduced and used in Task 3.   [1 mark]
Questions 3b, 3c, and 3d are related questions. You can use the information below in any part of Task 3.
(b) An official and a vehicle needed to be stored in the database.
The official’s name is Franklin Gateau from St Vincent and the Grenadines. Franklin is the only official from this country and the Chef De Mission for this country.
The vehicle is an ALPHARD manufactured by TOYOTA. You may assume that TOYOTA only produced one model called ALPHARD. The vehicle identification number (VIN) is 1C4SDHCT9FC614231, which seats up to 6 passengers.
Take the necessary steps in the database to record the required entries for this vehicle and official. When inserting this data, you may make up (invent) any other required information.   [5 marks]
(c)  Franklin booked two trips.
The first trip was booked for 30 July 2024 at 12:30 PM from Olympic and Paralympic Village to Porte de la Chapelle Arena, and it was scheduled to arrive 1 hour and 30 minutes later.
The second trip was booked for 30 July 2024 at 8:00 PM from Porte de la Chapelle Arena to Olympic and Paralympic Village, and it was scheduled to arrive 1 hour and 15 minutes later.
For both trips, the vehicle assigned was the Toyota Alphard with VIN 1C4SDHCT9FC614231; the allocated driver was Claire Robert (licence number: 55052a543210), and the preferred
language was English.
Take the necessary steps in the database to record the required trip entries. Both trip
bookings  must be treated as a single transaction. When inserting this data, you may make up (invent) any other required information.   [8 marks]
(d) As scheduled, on 30 July 2024 at 12:30 PM, Claire Robert picked up the St Vincent and the    Grenadines team from the Olympic and Paralympic Village and dropped them at the Porte de la Chapelle Arena. The actual trip took 1 hour and 45 minutes.
Then, at 5 PM on the same day, Claire got into an accident. Due to the short notice and the unavailability of other drivers, all booked (incomplete) trips allocated to Claire for the rest of the day must be cancelled (i.e. removed from the system). PAT informed the officials who    booked the trips and reimbursed them with taxi vouchers.
Make these required changes to the data in the database.   [6 marks]
TASK 4: DATABASE MODIFICATIONS (13 marks):
Your answers for these tasks (Task 4) must be placed in the supplied SQL script. T4-pat-mods.sql
The required changes must be made to the "live" database (the database after you have completed tasks 1, 2 and 3, in which other users must be assumed to be active). You MUST     not edit and execute your schema file again. Before completing the work below, please ensure you   have completed tasks 1, 2 and 3 above. If, in answering these questions, you need to create a table, please place a drop table statement immediately before your create table statement.
(a) PAT would like to store each official’s role. The list of roles, which includes General,
Administrator, Head Coach, Coach, and Physician, will remain unchanged. The default role is General. The Chef de Mission of each country must be assigned an Administrator role.
As part of your solution, provide appropriate select and desc statements to show the changes you have made. Select to show any data changes that have occurred, and desc tablename,    e.g., desc customer, to show any table structural changes.   [5 marks]
(b) PAT would like to allow complaints about the driver's behaviour on a particular trip. The official who requested the trip will submit these complaints. Multiple complaints may be lodged for a   particular trip. An official cannot make two complaints for a particular trip at the same time.
PAT provides some categories for the complaints. The current categories are late arrival, rude behaviour, poor driving, and failing to assist. Each category has a specific demerit point: a late arrival or failure to assist incurs one demerit point, and rude behaviour or poor driving incurs    two demerit points. PAT wants to add more categories in the future.
The system stores each complaint’s date, time, category, and detailed comment. It also stores the trip for which the complaint was made.
The PAT staff member follows up on the complaint and investigates whether it is valid. If it is, it will be flagged in the system as a valid complaint.Change the database structure to support these new business rules. You are not required to  add the complaint data (you must add the category data as listed in this task). You only need to provide the structure so PAT can store complaints.
As part of your solution provide appropriate select and desc statements to show the changes you have made. Select to show any data changes that have occurred and desc tablename     e.g.  desc customer to show any table structural changes.   [8 marks]



         
加QQ：99515681  WX：codinghelp  Email: 99515681@qq.com
