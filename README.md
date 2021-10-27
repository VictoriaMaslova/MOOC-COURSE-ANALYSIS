# E-learning courses analysis

![](https://www.linguahouse.com/linguafiles/md5/d3848eb1bb1f166441b1a2d4a574b4f6)

All educational platforms need to offer the easiest and the most engaging ways of delivering knowledge to its users, and reflect the education system offered by schools and universities — have different levels, scores, and, the most valuable feature for today, possess personal track of each student’s learning process. The global market of online courses based on machine learning technologies increased with the CAGR(The compound annual growth rate) higher than 16% by 2021!

ML technologies analyze the content of online courses and help to figure out whether the quality of the offered information meets the applicable standards on one hand, and on the other, it shows how the users perceive the data and do they understand what is taught. 

In this project, my main goal is  to discover the secret of designing an excellent online course for studying business analytics.

- What are the features of the Business Analytics online course?
- How is the course content introduced?
- How is the instructor introduced?
- What are the factors impacting the enrollments of the Business Analytics online course?

## File Structure:

```
ETL
|- ETL_nonText.ipynb            # notebook for process non-text information.
|- ETL_Text.ipynb               # notebook for process text information.
|- text_mining.py               # functions for text mining. 
model
|- Analysis.ipynb               # notebook for analysis the dataset. 
webscrap
|- get_course_list.py           # python scripts for getting course list.
|- get_course_data.py           # python scripts for getting course data. 
README.md
```

## Pipeline

![](https://github.com/VictoriaMaslova/MOOC-COURSE-ANALYSIS/blob/main/pipeline.png)
I use the package Selenium with Python to perform web scraping on the Udemy website. The list of 1005 courses is obtained from Udemy’s webpage for Business Analytics & Intelligence Courses. The information, such as enrollment number, course rating, and course description, is scrapped on each course’s web page. Hence, there are both numerical information and texts. Also I use Gensim to preform Latent Dirichlet Allocation (LDA) as a Topic model on the course description and the instruction introduction.


I analyzed text and non-text data to understand the key factors that have a sighnificant impact on students satisfaction.

```Original Price```

- Udemy has regularly \$10 per course promotion, so learners prefer to puchase course during the promotion instead of paying the original price. 
- The regression analysis shows that the original price has a positive impact on the enrolment number. 
- It can be explained that a high original price gives the learners an impression that this course is valuable. 
- Hence, we suggest the instructors set the course's original price as $199.99, which is the maximun value of the original price in the dataset.



```Lecture numbers```

- The lecture number has a positive impact on the enrollment number. 
- It can be explained that learner favor the course with a big number of short lectures. 
- The mean of course hours is 5 hours, and the mean of lecture number is 52. 
- Hence, we suggest the instructors set the lecture nubmer as round 100 and each lecture length as 3 minutes. 

```Downloadable Resources```

- The number of Downloadable Resources has a positive impact on the enrollment number.
- Considering the distribution of Downloadable Resources in the dataset, in which the mean value is 7, we suggest the instructors provide around 15 downloadable resources in the course.


```Course Description```

- The analysis above shows that the two topics in course descripiton, power bi visulization and project report involving sql, have an impact on the enrollment number. 
- This implies that the visulization content such as power bi and tableau should be highlighted in the course description. Learners are looking for the visulization skills. 
- The course projects that are set close to real-world industrial projects involving SQL database and formal reporting strategies should also be highlighted in the course description.

```Instructor Introduction```

- The analysis above shows that the two topics in instructor introduction, instructor in university and many years of experience, have an impact on the enrollment number. 
- This implies that learners emphasize on the instructor's educational background and teaching and researching experience in University, which should be highlighted in the instructor introduction. Does the instructor have a CS or business advance degree? Does the instructor teaching or researching business analytics in University?
- The instructor's long-time experience in bussiness analytics should also be highlighted in the course description. How many year does the instructor involving business analytics? How many year does the instructor use Python, machine learning, SQL, or Tableau?



## Conclusion

- To design an excellent online course for business analytics, we can increase the original price, lecture numbers, and downloadable resources to promote the enrollment of the course.
- The course description should emphasize the project reporting and visualization technologies such as SQL, Excel, and power bi.
- The instructor introduction should emphasize the instructor's teaching experience, especially teaching business analytics in a university for an extended period.
