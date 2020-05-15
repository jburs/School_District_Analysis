# School_District_Analysis

## Project Overview

using python and pandas, create an analysis for the given school district. Data created includes a general summary, individual school summary, high and low performing school, Math and Reading Scores by Grade, scores by school spending, scores by school size and scores by school Type. 

## Resources

Data Source: schools_complete.csv and students_complete.csv
software: 
  Jupyter natebook 6.0.1
  Python 3.7.4
  numpy 1.16.5
  pandas 0.25.1

## Challenge

for this section, 9th grader data from Thomas High school was considered incorrect, and replaced with np.nan using the loc function. The following details how this affected teh results. 

disctict summary: 
the avgerage reading score has remained the same, all other scores and %'s have decreased slightly. Very minimal changes to the data set as a whole. 

School summary:
This data is grouped by school name, and this only Thomas High School is affected, The average scores are minamally smaller, and there is a large decrease in the percent passing column. This is due to the per_school_counts variable from the following line:

per_school_counts = school_data_df.set_index(["school_name"])["size"]

This takes the school size from the original data set. Since we replaced data with NaN's, this number is no longer accurate. When we then use it for the calculations of the percent, we are escentially considering the NaN's as 0 since the number of scores summed is less than the total number of students. Thus, the percent columns are not accurate for Thomas High School. 

High and Low performing schools: 
Thomas High Scool has gone from 2nd highest % overall passing, to the 8th highest % overall passing. This is due to the inaccuracy of the % overall passing data for Thomas High school that was detailed eariler. 

Math and Reading Scores by Grade:
The Thomas High School math and reading scores by grade are only affected for the 9th grade. The output is now nan since we no longer have the 9th grade Thomas High school math or reading data. The 10, 11, and 12th grade scores remain unchanged as expected, since we did not alter their data. 

Scores by School Spending:
Thomas High School is in the $630-644 bracket. And thus only that row of data is affected. The Avg's remain the same, however the %'s dropped as expected due to the number of data points summed over being smaller than the total count it is divided by due to the nan in the data. This is due to the afore mentioned reason in school summary. 

Scores by School Size:
Thomas High school is a medium school. Thus, the %'s in the medium row have decreased significantly. The averages remain the same. 

Scores by School Type:
Thomas High School is a Charter. Therefore averages remian the same, and the percents decrease. This decrease is smaller than previous mentions due to the larger amount of data points in the charter category compared to earlier categories. This makes the difference between total data points, and schools counts much smaller, making the drop in %'s smaller. 

