Project 1

Libraries used: math, numpy, pandas, matplotlib

Dataset used: Stack Overflow Data - 2019 Survey

ATTN: Dataset not included in Github as it is too large. It is available from:
https://drive.google.com/open?id=1QOmVDpd8hcVYqqUXDXf68UMDWQZP0wQV

Business Understanding
	To perform a brief investigation into workplace happiness of Data industry professionals.
	By looking at the job and career satisfaction data by country, we can observe the countries,
	that rank highest and lowest in job and career satisfaction. This will give an indication of
	which countries or more specifically the type of workplace cultures that exist in these countries
	are most satisfying to data industry employees. 
    Then by observing the responses to the multiple choice questions in the survey regarding the
	workplace factors that attract employees (other than salary), and those that detract from 
	productivity (and hence overall work satisfaction).
Data Understanding
    Dataset used were the responses collected in the Stack Overflow 2019 Survey.
	Not all fields are filled, some contain null values.
	Responses to Job and Career satisfaction questions collected in 5-point Likert scale (from 
	‘Very dissatisfied’ to ‘Very satisfied’).
	Responses to multiple answer job factor attraction and productivity detractors questions
	contained as a single string seperated by the ';' character.
	
Prepare Data
    Firstly observed list of countries and count. Added columns JobSat_num and CarSat_Num to the
	dataframe, and transformed their responses into numerical values in order to calculate a mean
	using the following:
		'Very dissatisfied' = 0
		'Slightly dissatisfied' = 1
		'Neither satisfied nor dissatisfied' = 2
		'Slightly satisfied' = 3
		'Very satisfied' = 4
	Out of the 179 countries there were some with a very low number of responses. To ensure the
	sample size from each country is large enough, I decided to only include the data from countries
	with at least 50 responses to both questions. This reduces the country list to 89. I then constructed
	a new dataframe containing results only for those countries with high response rate and eliminating any 
	rows with null values. Taking the dataframe of high response countries, I created a dataframe of the
	Job and Career satisfaction means grouped by country.
	
	Answers to questions allowing multiple choices were contained in single strings separated by the ';'
	character. I defined a function split_string which would take the full answer string and return
	a list of the individual answer strings contained. Another defined function single_responses takes the
	column of answer strings, iterates through the object, adding individual answers found by the split_string
	function to the answers set, then returning the set contents.
	Passing the set of responses and the column object of responses from the dataframe to the response_counter
	function it iterates through the set of individual responses, calling the function find_string with each
	individual response. The find_string function iterates through the column object counting each time the
	individual response is found in the rows of the complete answers. The find_string returns a count, and
	the response_counter adds this and the individual response it was looking for, to a tuple list. The
	response_counter then returns this tuple list where it is saved as a new dataframe. The dataframe created
	is used for the creating the graphs for observation of the proportion
	
Data Modeling
    Question 1
		- What are the top and bottom 10 countries in relation to Job Satisfaction?
		
		Using the dataframe of mean Jobs and Career Satisfaction values, I displayed the top 10 countries
		of the dataframe, sorted by Job Satisfaction, then displayed the bottom 10 by sorting them in descending
		order.
        
https://miro.medium.com/max/827/1*GsyO1W5yQPjGYZKCxOotxA.jpeg
		
    Question 2
        - What are the top and bottom 10 countries in relation to Career Satisfaction?
		
		Using the dataframe of mean Jobs and Career Satisfaction values, I displayed the top 10 countries
		of the dataframe, this time sorted by Career Satisfaction, then displayed the bottom 10 by sorting them in descending
		order.
		
https://miro.medium.com/max/761/1*Wss4UNrdhIT4sOCrQCRRaQ.jpeg
		
	Question 3
        - What factors are most important when an employee is selecting a particular job (other than money)?
		
		Taking the responses from the JobFactors column, I created a new dataframe and removed the null
		responses. Using the single_responses function I created a list of the unique single responses. Then
		I created a dataframe using the response_counter which counts each time that single answer appears in
		a response string. I was then able to create a horizontal bar graph of the proportions.
		
https://miro.medium.com/max/721/1*M7ZxYMaHqCbYPdxj4kwFTg.png
	
	Question 4
        - What are your greatest challenges to productivity as a developer?
        
		Similar to the above, but used the WorkChallenges column.
		
https://miro.medium.com/max/721/1*londEZaphYaTy31SMpQIrA.png
		
Evaluation

    Findings
	
	Findings as stated in the project summary. 
	Western Countries topped most satisfied countries in Jobs and Career
	Satisfaction. Asian, African and South American counties represented least satisfied in Jobs and Career
	Satisfaction. 
	Office/Workplace culture, and languages used were most important to employees other than money.
	A distracting work environment, meetings, and non-developmental work were the most challenging factors 
	for employees.
