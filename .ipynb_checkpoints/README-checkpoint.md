# STATEMENT OF WORK

**1. Database ERD**

  First, we made our Entity Relationship Diagram for the database, as you can see below.
    
   For  our Database ERD we decided to go with 4 entities/tables. For the Database these entities were "INSTRUCTOR", "CATALOG_DESC", "COURSE_OFFERING", and "COURSE_MEETING".
   
![CourseDataDB_ERD](docs/CourseDataDB_ERD.png)

**2. Creating the Data Dictionary**
    
   We went through each of our attributes within the Database ERD and studied the data in the various csv's to understand exactly what we were working with. We then defined the attributes so that anyone with access to the Data Dictionary would be able to understand and use the database themselves.
   
   Link to [Data Dictionary](docs/DataDictionary.md)

**3. Creating the Database and Creating/Populating the Tables**

   We created our database in a Jupyter Notebook by using the %%sql and sqlite link to create a new database called CourseData.db. This created us a brand new database with no tables or anything. It was totally empty.
  We used CREATE TABLE queries to create each one of our entities from the ERD, and defined the attributes/columns of each entity/table by their type, and Null/Not Null constraints. 
  
   Next we had to import all of the data from the csv files into our database. We used the terminal to create three separate tables from our database so that we could more easily import the csv's. These tables were import_course_meetings, import_courses, and import_catalogs. We used sqlite to upload all of our csvs by category into those three tables, and then used the three tables in order to run our INSERT's.
     
   We then ran INSERT INTO SQL queries to populate our database tables by selecting data from the import tables to fill our database. We had to use JOIN's to make sure that the tables would link and often used SELECT DISTINCT's to make sure we didn't overpopulate and make the database too big.
   
   [CourseDataETL](docs/CourseDataETL.ipynb)
      
**4. CourseData Testing and Demo**

[CourseData Testing](docs/CourseDataTests.ipynb)

**5. Running SQL Queries and Testing Integrity**

   *Test for Entity Integrity*: Ran SQL Queries to check that our COUNT's and DISTINCT COUNT's for the tables were equal. This ensured that we had no duplicates in our database.
   
   *Test for Domain Integrity*: Checked to make sure that our data types matched up and would work within the restrictions of SQL/sqlite, as well as making sure that they made sense given what each attribute was defined as in our Data Dictionary.
   
   *Test for Referential Integrity*: To test for referential integrity, we had to use a lot of JOIN's to make sure our foreign keys and primary keys matched up to link the tables. In order to check this to make sure our database satisfied this integrity constraint, we ran queries to call data we already knew, such as information about this class. Once the data was returned, we could confirm that it was correct and therefore our database satisfied referential integrity.
    
**6. Data Warehouse ERD**
   
   For the Data Warehouse, we went with 4 entities as well: "DW_COURSE_OFFERING", "DW_INSTRUCTOR", "DW_COURSES", and "DW_ CATALOG_DESC".
    ![CourseDataDW_ERD](./docs/CourseDataDW_ERD.png)
    
**7. Github Issues**

   We had some trouble with JOIN's and ended up accidentally querying 70,000,000 rows of data from our database somehow. This made our repo size way too big and made it impossible for us to push, even after using the vacuum; method to shrink it. We had to get help from Dr. Tao and Yue Pu in order to resolve our issue. 
   
   We had to move the database itself onto Mike's computer, and then Yue was able to delete out the repository, so that we could reclone it and reupload the database to continue working.
   
   Another issue we had was that we dropped our import tables early on in order to decrease our repo size, but as soon as we ran through our notebooks again, we realized we had deleted out all of our data and needed to repopulate the database. We tried to restore a previous commit on github, but our most recent commit had been before we imported the data.

**8. Creating the Data Warehouse and Creating/Populating the Warehouse Tables**

   To create the Data Warehouse, we cloned our original CourseData.db and built out our dimension tables from that. We used the same methods for this as we did when originally creating the database, and created two new aggregates to make querying simpler. We focused on counting the number of preps each teacher has to make for a given year, Summer, Fall, and Spring. This allows us to gauge whether or not teachers are being overworked and if there is a need to hire a new faculty member. We focused on this by department, choosing to look at the accounting faculty for this notebook. 
   
   Next we looked at the number of classes taught in the same given year, to compare to the number of preps. A prep is the planning that goes into teaching a unique class, but classes taught could be the same class taught across multiple sections, which would be more classes taught but only one prep created. This allows us to see who is really overworked versus who is simply teaching the most classes.
  
   [CourseDataWarehouseETL](docs/CourseDataWarehouse.ipynb)

  
**11. Testing and Demo on the Data Warehouse**

[CourseDataWarehouse Testing](docs/CourseDataWarehouseTest.ipynb)

[CourseDataWarehouse Demo](docs/CourseDataWarehouseDemo.ipynb)
