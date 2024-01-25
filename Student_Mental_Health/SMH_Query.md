### Question we want to answer?
How does the length of stay impact the mental health 
of the international students present in the study?
#### Run this code to see the dataset you are working with.
```sql
SELECT * 
FROM 'students.csv' AS students;
```
#### Now select the required .
```sql
SELECT stay, 
COUNT(inter_dom) AS count_int, 
ROUND(AVG(todep),2) AS average_phq, 
ROUND(AVG(tosc),2) AS average_scs,
ROUND(AVG(toas),2) AS average_as,
FROM students.csv AS students
WHERE inter_dom = 'Inter'
GROUP BY stay
ORDER BY stay DESC;
```
### Explanation

The provided SQL query performs an analysis on student data with a focus on international students (`inter_dom = 'Inter'`). Below is a breakdown of the key components of the query:

- **SELECT Clause:**
  - `stay`: Represents the duration of stay.
  - `count_int`: Presents the count of international students.
  - `average_phq`: Indicates the rounded average of the `todep` column (presumably a measure related to PHQ).
  - `average_scs`: Represents the rounded average of the `tosc` column (potentially related to SCS).
  - `average_as`: Reflects the rounded average of the `toas` column.

- **FROM Clause:**
  - The data is sourced from the `students.csv` file, which is given the alias `students`.

- **WHERE Clause:**
  - Filters the data to include only records where the `inter_dom` column is equal to 'Inter', effectively selecting international students.

- **GROUP BY Clause:**
  - Groups the data by the `stay` column, providing aggregated results for each unique duration of stay.

- **ORDER BY Clause:**
  - Orders the result set in descending order based on the `stay` column, providing a descending order of duration of stay.

### Result
The final result is a summarized analysis, showcasing the count of international students and the rounded average values for various factors based on the duration of their stay. This analysis can offer insights into patterns or trends among international students with different lengths of stay.
