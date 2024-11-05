# Student Grade Map Project

### Excel | SQL | Python | Tableau 

### How can we quickly identify and predict which incoming freshmen will struggle academically? Can students' addresses or neighborhoods predict which students will struggle?

 - Student Grade and address data was taken from the school's Student Information System (SIS) and exported to Excel as two separate files
 - Data was cleaned in Excel to remove null values, duplicate records, etc.
 - Several other columns were kept in addition to grades and addresses. Ethnicity and income are known related variables to students' academic performance.
       Would students' addresses be more predictive of their performance than other variables, which are known to correlate with student failure rates?
 - GPS coordinates were linked to student addresses and the number of failed courses for each student was calculated in SQL Server

   ### SQL Server Query:
   ![SQL Grade Address Join](https://github.com/user-attachments/assets/75577a63-d115-4758-b8b0-d7536b33babb)
  
## Data Visualized in Tableau

### Rate of Failures as a Function of Fee Waiver

Students from lower-income families can qualify for free or reduced-price school lunches, depending on income, number of dependents, etc. This is generally known as a fee waiver and serves as a convenient way of measuring a family's income. This is often used as a metric by which students and families can qualify for other supports. It is well-documented that students who qualify for free or reduced school lunches tend to have higher rates of academic difficulty.

The same is true in this data. In the freshman class, 90% of the failed courses were failed by students with a fee waiver while these students only make up 35% of the freshman population. This is most striking in the freshman class, but the same disproportion is found in sophomore, junior, and senior classes.

### What Percent of Failed Classes are Failed by Students on Fee Waiver?
![Fee Waiver](https://github.com/user-attachments/assets/32997269-bc8e-49c9-bed2-60f400b383b3)

### Rate of Failures as a Function of Ethnicity

Ethnicity is another demographic known for disproportionate student outcomes. This student data also displays disproportion, but the representation of the ethnic groups is somewhat surprising. In the freshman class, Hispanic students make up 25% of the population and account for 50% of the failures, while Black students' numbers are 9% and 20% respectively. Both groups' proportion of failed classes is 2x their population proportion. Meanwhile, in the sophomore class, black students are doing proportionally much worse. They make up 7% of the population and 22% of the failures, while Hispanic students' numbers are 20% and 25% respectively.

### What Percent of Failed Classes are Failed by Each Ethnicity?
![Ethnicity](https://github.com/user-attachments/assets/9a45f98e-11c7-4130-83de-c60173a7d6fc)

### Rate of Failures as a Function of Address

Finally, students' neighborhoods were analyzed. The GPS coordinates were disguised by creating a random set of values by which the longitude and latitude were adjusted. A set of random values was created using Python and added to the real longitude and latitude values in Excel. The adjustments were kept small to preserve the distribution of student failures, yet hide the true address of students who failed courses. The adjustment caused the data point to move in a random direction and by a random amount, but not more than about 600 feet.

 ### Python Code:
  ![GPS-adjustment-python](https://github.com/user-attachments/assets/65adc669-c70b-4688-8c7b-bb0e36894e6e)

The number of classes failed was represented by both the size and color of the point to highlight areas where Fs are more common. Tableau's built-in census maps were used as the backdrop - "Renter Occupied Housing Units" was used to highlight the prevalence of both lower net worth areas and lower-income families. The general point density also highlights the high school-age population density

 ### Student Grade Map 
   ![StudentGradeMap](https://github.com/user-attachments/assets/f499534c-d586-4ef4-9b73-c7643798793f)![Legend](https://github.com/user-attachments/assets/3fbb5378-4b2b-45ad-acb9-91ce986a7a06)

 ### Summary
There is certainly a clustering of failed classes originating from an area in the Northeast corner of the town, where there is also a higher rate of rented housing units. However, because of the population density and the large number of students living in that region who did not fail any classes, student addresses or neighborhoods does not predict student failures completely. Ethnicity is also a risk factor, but fee waiver stands out as being the most significant variable and a better single predictor of class failure. While there is already an overlap between these two variables, considering them together likely produces the most accuracy when predicting which freshmen will fail courses.
    
