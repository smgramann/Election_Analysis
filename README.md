# Election-Audit with Python

## Overview of Project

### Background
The election commission received information on the winner of a congressional election and after reviewing the results they’d also like to understand voter turnout in each county, the percentage of votes from each county, and the county with the highest turnout.  Additional analyses have been conducted to provide that information.

### Purpose
Starter code was provided to kick off the analysis; however, ‘for’ loops and conditional statements with membership and logical operators code needed to be written to achieve the objectives.  The added code allowed for the requested county information to be provided to key stakeholders for understanding and decision-making.

## Election-Audit Results

### Total Votes Cast
For this congressional election, 369,711 total votes were cast across three counties.  This result was determined by first creating a total_votes variable and setting that to zero and creating a ‘for’ loop to iterate through the results file and increase total votes by one for each row.

![Total_Votes_Variable](https://user-images.githubusercontent.com/80165223/114238831-db408380-994a-11eb-8a6f-6fee851876ff.png)



### Votes at County Level
Within the ‘for’ loop mentioned above, an ‘if’ statement was written to check and see if the county did not match an existing county in the county list.  If it did not match any county it was appended to the county list and the votes were tallied for that county.  See the code below:  


![County_List_For_Loop](https://user-images.githubusercontent.com/80165223/114238907-f57a6180-994a-11eb-99ca-0e36bce5cf24.png)



The percentage of total votes in each county were then calculated and printed by establishing two new variables and dividing votes by overall votes for each county.  See the code below: 


![county_percentage_of_votes](https://user-images.githubusercontent.com/80165223/114238948-01662380-994b-11eb-9852-340b4d2723b3.png)


This resulted in determining the following county turnout and percentage of overall votes:

Jefferson:  10.5% (38,855 votes)
Denver:  82.8% (306,055 votes)
Arapahoe:  6.7% (24,801 votes)

### County with Largest Number of Votes
The county with the largest number of votes was determined within another ‘for’ loop utilizing an ‘if’ statement to identify if the current county being analyzed has the greater number of votes.  The votes_county_turnout variable was the county with largest number of votes, which was Denver County.  See the code below:


![County_Highest_Votes](https://user-images.githubusercontent.com/80165223/114238988-117e0300-994b-11eb-9dd3-5c63d1998f8f.png)


### Total Votes Received by Candidates
Similar to total votes at the county level, total votes received by each candidate were extracted using a ‘for’ loop with an ‘if’ statement to append a candidate’s name to the candidate options list if it did not match an existing candidate in analysis and then track each vote for that candidate’s name.  See code below:


![Candidate_Votes](https://user-images.githubusercontent.com/80165223/114239027-222e7900-994b-11eb-899b-378f8302901d.png)


The percentage of total votes for each candidate were then calculated and printed by establishing two new variables and dividing votes by overall votes for each county.  See the code below: 


![percentage_candidate_votes](https://user-images.githubusercontent.com/80165223/114239087-35414900-994b-11eb-9631-071166f6d26b.png)


This resulted in the following total vote counts and percentage of votes received by each candidate:

Charles Casper Stockham: 23.0% (85,213 votes)

Diana DeGette: 73.8% (272,892 votes)

Raymon Anthony Doane: 3.1% (11,606 votes)


### Winning Candidate
The winning candidate was determined by creating an ‘if’ statement to identify the candidate with the highest number of votes and percentage of votes.  Code was then written to print to terminal and write to a text file with specific formatting for multiple dictionaries.  See the code below:


![winning_candidate](https://user-images.githubusercontent.com/80165223/114239143-4a1ddc80-994b-11eb-9e05-a1c2238f36f0.png)


The winning candidate is as follows:

Winner: Diana DeGette

Winning Vote Count: 272,892

Winning Percentage: 73.8%

## Election-Audit Summary

The code written worked well for identifying candidate votes, county turnout, and overall winner; however, it can be modified to serve other purposes.  

If data were provided on the method by which each person voted (in person, absentee ballot, early/mail-in, etc) a better understanding could be gained to ensure future policy allows for easy voting access based on voter preference and trends.  This could be accomplished by swapping out all code related to the county level detail and, instead, be voter method related. 

First,  a method_list and method_votes dictionary would need to be established to track method and number of votes via each method.  Example:

method_list = []

method_votes = {}

Second, rather than iterating through the results file for county vote information and checking to see if a vote method matches an existing method in the list then tallying the count, the code would look like this:

	if method_type not in method_list:
		method_list.append(method_type)
		method_count[method_type] = 0
	method_count[method_type] += 1

Having this type of information would allow government to best serve their constituents.	
