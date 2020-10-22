Project 1

Dataset used: Stack Overflow Data - 2019 Survey

ATTN: Dataset not included in Github as it is too large. It is available from:
https://drive.google.com/open?id=1QOmVDpd8hcVYqqUXDXf68UMDWQZP0wQV


Questions:

Part 1
Top 10 & Bottom 10 countries in Job satisfaction
Top 10 & Bottom 10 countries in Career satisfaction
Part 2
Investigate proportion and distribution of unique answers to the following multiple choice questions
Q: Imagine that you are deciding between two job offers with the same compensation, benefits, and location. Of the 	following factors, which 3 are MOST important to you? &
Q: Of these options, what are your greatest challenges to productivity as a developer?

Part 1 Coding:

-Read the dataset into a dataframe using pandas read_csv function
-Explored the data by observing 'Country' column using groupby, plotting a graph
-Created a Dataframe of unique country names
-Explored the data by observing 'JobSat' & 'CareerSat' columns using groupby
-Converted responses in 'JobSat' & 'CareerSat' columns to numerical values
  'Very dissatisfied' = 0
  'Slightly dissatisfied' = 1
  'Neither satisfied nor dissatisfied' = 2
  'Slightly satisfied' = 3
  'Very satisfied' = 4
-Created a dataframe with results only from countries that had 50 or more responses to the 'JobSat' and 'CareerSat' questions to ensure the sample size was large enough to estabish an accurate mean.
-Created dataframe Country_JobCareer_Sat with means of all countries. Printed the 4 tables of top/bottom 10 using using sort and groupby.

Part 2 Coding:

-Explored responses to the questions, noting the questions allowed multiple answers seperated by ';'
-Defined functions split_string and single_responses to enable extraction of single answers from the response strings.
-Extracted all answers as a list, and unique answers as a set.
-Defined functions find_string and response_counter to search through the column of response answers for each of the unique responses to find the count of each, and return a list of response and counts.
-Plot the results in a horizontal bar chart.

