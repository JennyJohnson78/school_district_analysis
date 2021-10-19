# School District Analysis
## Overview
Data Scientist Maria needed assistance analyzing data on student funding and standardized test scores. City School Data was aggregated to showcase trends in school performance to help the City School Board make decisions about school funding. However, the school board has notified Maria and her supervisor that one of the csv files shows evidence of academic dishonesty at Thomas High School in regards to the reading and math grades. These grades appear to have been altered. To ensure the analysis is accurate, the math and reading scores need to be replaced for Thomas High School with NaNs while keeping the rest of the data intact. After this has been completed, a new analysis will need to be completed and compared to the original analysis.

## Results
- **How is the district summary affected?**

After importing NumPy, set all Thomas High School 9th grade math and reading scores to "NaN" via the code below:

```
student_data_df.loc[(student_data_df["grade"]== "9th") & (student_data_df["school_name"]== "Thomas High School") , "reading_score"] = np.nan
```
```
student_data_df.loc[(student_data_df["grade"]== "9th") & (student_data_df["school_name"]== "Thomas High School") , "math_score"] = np.nan
```

The district summary was affected slightly. The percentage of students passing math declined by 0.4% and the percentage of students passing reading declined by 0.1%. The overall passing grade dropped from 65.2% to 64.9%.

![image](https://user-images.githubusercontent.com/67409852/137867045-0db7d492-81a1-453e-aec3-9a14468e0c77.png)

![image](https://user-images.githubusercontent.com/67409852/137867504-85f09b06-00e1-452c-bfd1-0367d0938a9c.png)

- **How is the school summary affected?**

In regards to the school summary, nothing is changed when it comes to the 14 other schools. However, when it comes to Thomas High school, there is a clear difference. When it comes to the percentage passing math, there was a drop from 93.3% to 66.9%. The percentage passing reading dropped from 97.3% to 69.7%, and the percentage of students passing overall dropped from 90.9% to 65.1%.

![image](https://user-images.githubusercontent.com/67409852/137869699-aed653b7-c46b-414f-93fe-5a84be7e32fe.png)

![image](https://user-images.githubusercontent.com/67409852/137870297-1c2e3083-303c-44a8-b87a-a2b7052176a5.png)

- **How does replacing the ninth graders’ math and reading scores affect Thomas High School’s performance relative to the other schools?**

In comparison to the other schools in the district, Thomas High School went from 2nd in overall passing percentage, down to 8th.

- **How does replacing the ninth-grade scores affect the following:**
  - Math and reading scores by grade:
  
    Because all of the grades are set to NaN, they are equivalent to failing. The number of students at Thomas High School with a math grade dropped from 1635 to 1174. The           percentage passing score is greatly reduced.
    
  - Scores by school spending:
  
    Thomas High School is still in the spending bucket/ range of $616-$645. They will still receive the same amount of money per student.
    
  - Scores by school size:
  
    Thomas High School is still in the medium school size bucket/range of 1,000 to 2,000. The size of the student body did not change.

  - Scores by type:
  
    Thomas High School is a charter school. The scores for charter schools did not change.
