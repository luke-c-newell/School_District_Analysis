# School District Analysis
## Overview of the school district analysis
Working alongside the chief Data Scientist from a local school district, I have been asked to create an analysis of school performance in the district, to enable a comparison between schools. This analysis will be used to inform future decision making at the school and district level regarding the school budgets. The school district analysis will consist of the following:

- A district summary
- A school summary
- A table showing the top 5 and bottom 5 performing schools, based on the overall passing rate
- A comparison of the average math and reading scores for each grade level from each school
- A comparison of the school spending per student, by school size, and by school type

In addition, the school board has notified us that the student data file shows evidence of academic dishonesty; specifically, the reading and math grades for Thomas High School ninth graders appear to have been altered. Although the school board does not know the full extent of the academic dishonesty, they want to uphold state-testing standards and have turned to us for help. In order to ensure academic rigour, I will replace the math and reading scores for Thomas High School with NaNs while keeping the rest of the data intact. I also will then repeat the school district analysis and describe how these changes have affected the overall analysis.
## Results
- At the total district level, the headline results were not affected by the removal of the Thomas High School (THS) 9th grade results
- For the school summary, THS saw a decrease in the % overall passing score but remained as the #2 school in the district
- Replacing the THS math and reading scores for the 9th grade did not affect the relative performance compared to other schools in the district
- THS saw a reduction in the average math score and an increase in the average reading score, when removing the 9th grade results
- The schools in spending range $630-644 saw a decrease in the overall passing % when the THS 9th grade results were removed
- The Medium size schools saw a reduction across all the statistics when the THS 9th grade results were taken out of the analysis
- The charter schools saw a decrease in the overall passing % after removal of the THS results
### Metrics
A summary of the changes for Thomas High School after the 9th grade results were removed:
- Total School Budget was unchanged
- Per Student Budget was unchanged
- Average Math Score decreased
- Average Reading Score increased
- % Passing Math decreased
- % Passing Reading decreased
- % Passing Overall decreased

### How is the district summary affected?
At the total district level, the headline results were not affected by the removal of the Thomas High School (THS) 9th grade results
#### District summary (original)
![District_Summary_Original](https://github.com/luke-c-newell/School_District_Analysis/blob/main/Resources/District_Summary_Original.png)
#### District summary (with THS 9th math and reading grades omitted)
![District_Summary_THS_9th_omitted](https://github.com/luke-c-newell/School_District_Analysis/blob/main/Resources/District_Summary_THS_9th_omitted.png)
### School Summary
For the school summary, THS saw a decrease in the % overall passing score but remained as the #2 school in the district
#### School summary (original)
![School_summary](https://github.com/luke-c-newell/School_District_Analysis/blob/main/Resources/School_summary.png)
#### School summary (with THS 9th math and reading grades omitted)
![School_summary_THS_9th_omitted](https://github.com/luke-c-newell/School_District_Analysis/blob/main/Resources/School_summary_THS_9th_omitted.png)
### How does replacing the ninth graders’ math and reading scores affect Thomas High School’s performance relative to the other schools?
THS saw a reduction in the average math score and an increase in the average reading score, when removing the 9th grade results
#### Math and reading scores by grade
##### Math (original) ------------------ Math (with THS 9th omitted)
<img src="https://github.com/luke-c-newell/School_District_Analysis/blob/main/Resources/Math_summary.png" width="225"/> <img src="https://github.com/luke-c-newell/School_District_Analysis/blob/main/Resources/Math_summary_THS_9th_omitted.png" width="225"/> 

##### Reading (original) --------------- Reading (with THS 9th omitted)
<img src="https://github.com/luke-c-newell/School_District_Analysis/blob/main/Resources/Reading_summary.png" width="225"/> <img src="https://github.com/luke-c-newell/School_District_Analysis/blob/main/Resources/Reading_summary_THS_9th_omitted.png" width="225"/> 

### Scores by school spending
The schools in spending range $630-644 saw a decrease in the overall passing % when the THS 9th grade results were removed
#### Scores by school spending (original)
![Spending_Summary](https://github.com/luke-c-newell/School_District_Analysis/blob/main/Resources/Spending_summary.png)
#### School spending summary (with THS 9th math and reading grades omitted)
![Spending_Summary_THS_9th_omitted](https://github.com/luke-c-newell/School_District_Analysis/blob/main/Resources/Spending_summary_THS_9th_omitted.png)
### Scores by school size
The Medium size schools saw a reduction across all the statistics when the THS 9th grade results were taken out of the analysis
#### Scores by school size (original)
![Size_Summary](https://github.com/luke-c-newell/School_District_Analysis/blob/main/Resources/Size_summary.png)
#### School size summary (with THS 9th math and reading grades omitted)
![Size_Summary_THS_9th_omitted](https://github.com/luke-c-newell/School_District_Analysis/blob/main/Resources/Size_summary_THS_9th_omitted.png)
### Scores by school type
The charter schools saw a decrease in the overall passing % after removal of the THS results
#### Scores by school type (original)
![Type_summary](https://github.com/luke-c-newell/School_District_Analysis/blob/main/Resources/Type_summary.png)
#### School size summary (with THS 9th math and reading grades omitted)
![Type_summary_THS_9th_omitted](https://github.com/luke-c-newell/School_District_Analysis/blob/main/Resources/Type_summary_THS_9th_omitted.png)
## Summary
There were a number of changes that were made to the overall analysis after removal of the reading and math scores for the ninth grade at Thomas High School. I have highlighted the changes below.
### Major changes to the school district analysis
1. THS saw a reduction in the average math score and an increase in the average reading score, when removing the 9th grade results
2. The schools in spending range $630-644 saw a decrease in the overall passing % when the THS 9th grade results were removed
3. The Medium size schools saw a reduction across all the statistics when the THS 9th grade results were taken out of the analysis
4. The charter schools saw a decrease in the overall passing % after removal of the THS results
## Code sample and reading/math score removal
This code was used to remove the scores for Thomas High School 9th grade students and replace them with NaN values.
```
thomas_9th_count_df = school_data_complete_df.loc[(school_data_complete_df["school_name"] == "Thomas High School") & (school_data_complete_df["grade"] == "9th")].count()["Student ID"] 
```
This is a visualization of the result for a sample of 10 THS students
![NaN sample](https://github.com/luke-c-newell/election_analysis/blob/main/Resources/NaN_sample.png)