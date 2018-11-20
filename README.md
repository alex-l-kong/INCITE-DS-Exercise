# INCITE Data Science Exercise

## Presentation Format

You may view my findings for each part as a Jupyter notebook or as an HTML file. I chose to include my analyses in comments as well as printouts and graphs to support my findings. You can view an overview of the analyses conducted in this README for each part.  
  
Make sure you choose "Run All" if you want to rerun my code in the Jupyter notebook, as there are dependencies between cells.  
  
I have included a requirements.txt listing all of the libraries I used and the respective version.  
  
## Findings Part 1

I investigated the distribution of schools and departments and found 1 and 14 respectively. Although this example only saw us working with one school's data, it's important to understand the distribution of schools and departments as departments vary with school and thus our analyses will need to factor in the various distributions of departments schools may contain.  
  
The syllabi per department was determined to be highly variable. This means that a simple analysis of the number of times "Office Hours" appears in syllabi per department may not be so helpful. Departments with more syllabi would be expected to include the term "Office Hours" more. I chose to use "AOHPD", or "average OH per department", as a more complete metric to analyze. It was determined that, while AOHPD was imbalanced as well, it was imbalanced with a different distribution than number of syllabi. It was also found that many departments have less than 1 OH ("Office Hours" and its derivatives) mention per syllabus.  

## Findings Part 2

I decided to first extract the context OH (and its derivatives) appeared in each syllabi, and subsequently extracting times from that context identifying that as being the OH time with high probability. It was determined that:  
  
* Some syllabi didn't list the term "Office Hours", confirming our findings from part 1
* The context of "Office Hours" is highly variable
* Multiple OH are offered per course in some cases
* Times do tend to be in close proximity to "Office Hours"
  
By running the extraction process, most of the OH times were isolated. Further preprocessing would remove those outliers and group times based on starting and ending times.  
  
Just from the printout, it seems like a good deal of OH would be offered during 12-4, making this a possible "rush hour" time. Due to the complexity of analysis, though, I limited to 20 records, so this is a very nonrepresentative conclusion.  
  
I later extracted from the same contexts the days OH were held. For this part, I used 100 records. It was determined that, for these 100 records, Tuesday and Thursday tend to be very popular days for OH, while Wednesday and Friday not so much. However, more analysis will need to be conducted to back that claim up.  

## Findings Part 3

I chose to extract three variable for further analysis:
  
* Average length of syllabi per subject ("ALSPS"): a good syllabus should clearly outline the course goals and list necessary correspondance. A syllabus that's too short or too long may negatively affect students in the course, and if consistent across a department, the whole program. It was found that the average length of syllabi was highly variable and quite surprising in certain cases (ex. physics has a short length overall).
* Percentage of syllabi with prereqs: prerequisites ensure that students have a solid understanding of the material before moving on. The lack of prereqs could indicate the lack of education being provided in a particular domain. Relative to the total number of syllabi, it was found that the percentage of syllabi with prereqs does not follow a correlated pattern. In fact, some departments have a large number of syllabi yet very few that mention anything related to prereqs. That may just be due to the structure of the department, but it could also be due to the way professors teach the course.
* Percentage of syllabi with TA/total TA mentions: probably the most interesting metric analyzed. As touched on in Part 1, TAs are a major contributing factor to the teaching experience, as they provide additional help to students. Additionally, they help grade assignments, provide feedback to the instructor, and other crucial tasks. It was discovered that several departments were short on TAs, with some having close to 0. There is almost no correlation with the number of TAs mentioned on the syllabus and the percentage of syllabi containing TAs. This could mean that there is an imbalance in the distribution of TAs per department, with some courses requiring many TAs and a majority of others requiring few or even 0.

## In Summary

All of these parts require analysis to find metrics which may contribute to varying degrees to developing a strong index for measuring the degree of liberal arts education for specific programs. Teaching takes many different dimensions and forms, and not all contributing factors fall in the classroom alone. It thus takes many different variables to create this index, and only a few out of several candidates were considered. Further analysis needs to be conducted to create a suitable index by which to measure liberal arts offerings.