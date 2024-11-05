# Student Grade Map Project

### Excel | SQL | Python | Tableau 

### How can we quickly identify and predict which incoming freshmen will struggle academically? Can students' addresses or neighborhoods predict which students will struggle?

 - Student Grade and address data was taken from the school's Student Information System (SIS) and exported to Excel as two separate files
 - Data was cleaned in Excel to remove null values, duplicate records, etc.
 - Several other columns were kept in addition to grades and addresses. Ethnicity and income are known related variables to students' academic performance.
       Would students' addresses be more predictive of their performance than other variables, which are known to correlate with student failure rates?
 - GPS coordinates were linked to student addresses and the number of failed courses for each student was calculated in SQL Server

   ### SQL Server Query:
   ![](images/YerglerBen2022-23.JPG)

### Making Student Addresses Anonymous
- The GPS coordinates were disguised by creating a random set of values by which the longitude and latitude were adjusted.
- A set of random values was created using Python and added to the real longitude and latitude values in Excel
- The adjustments were kept small (within 500 feet) to preserve the approximate location and distribution of student failures

   ### Python Code:
   ![](images/GPS-adjustment-python.jpg)
  
### Data Visualized in Tableau
- The number of classes failed was represented by both the size and color of the point to highlight areas where Fs are more common
- Tableau's built-in census maps were used as the backdrop - "Renter Occupied Housing Units" was used to highlight the prevalence of both lower net worth areas and lower-income families
- The general point density also highlights the high school-age population density
  
    ### Student Grade Map 
    ![](images/StudentGradeMap.jpg)
