# **Data Dictionary**

This is our Data Dictionary according to the csv files we used to import our data and populate our database.

## **INSTRUCTOR Entity**

*instructor_id* : surrogate primary key to identify instructor uniquely, because many instructors teach multiple classes

*primary_instructor* : First name and last name of the instructor

## **CATALOG_DESC Entity**

*catalog_desc_id* : surrogate primary key to identify catalog descriptions uniquely, because other attributes/columns of this table yield duplicates

*catalog_id* : this is the course number and subject of the course

*program_code* : specific program code within each department for course (Ex: TX = Taxation)

*program_name* : specific program name within each department for course(ex: Taxation falls under Accounting)

*course_title* : title of the course

*prereqs* : the previous requirements necessary to enroll within this course. Can refer to academic standing, major, or classes required to complete

*coreqs* : any courses or labs that are required to be taken at the same time as the course at hand

*fees* : any fees in addition to the full tuition attributed to each course

*attributes* : university core requirements that are satisfied upon completion of the course

*description* : description of the course subject matter

*catalog_year* : year in which this given course was offered

*credits* : credit amount attributed to the course by the University, can be between 1 and 3

## **COURSE_OFFERING Entity**

*course_offering_id* : surrogate primary key to identify course offering uniquely, because other attributes/columns of the table yield duplicates

*CRN* : Course Reference Number used to identify the course

*term* : the term (Fall, Winter, Spring, Summer) that the course is being offered, followed by the year

*section* : unique identifier of each separate grouping of students for a given class

*title* : title of the course

*credits* : credit amount attributed to the course by the University, can be between 1 and 3

*cap* : the University capacity of students who can enroll in the course

*act* : the actual amount of students enrolled in the course

*rem* : the amount of open spaces remaining for students to enroll in the course

*meetings* : the location, date, days of week the course meets, and time of day the course meets, stored with keys as a dictionary

*timecodes* : the location as well as days of the week and time of day that the course meets

*catalog_year* : year in which this given course was offered

*catalog_id* : this is the course number and subject of the course

*instructor_id* : surrogate primary key to identify instructor uniquely, because many instructors teach multiple classes

*catalog_desc_id* : surrogate primary key to identify catalog descriptions uniquely, because other attributes/columns of this table yield duplicates

## COURSE_MEETING Entity

*meet_id* : surrogate primary key used to identify course meetings because other attributes/columns yield duplicates

*location* : the room number and name of University building that the course is held in

*day* : one letter designation for the day of the week of the class meeting 
[Monday:M, Tuesday:T, Wednesday:W, Thursday:R, Friday:F, Saturday:S, Sunday:U]

*start* : date and time(military) that the course meeting begins

*end* : date and time(military) that the course meeting ends

*CRN* : Course Reference Number used to identify the course

*term* : the term (Fall, Winter, Spring, Summer) that the course is being offered, followed by the year

*course_offering_id* : surrogate primary key to identify course offering uniquely, because other attributes/columns of the table yield duplicates
