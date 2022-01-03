# 			Data Visualization and Analytics Bootcamp - Challenge 1
# 							Student: Ron Hankey
# 							Date: January 3, 2022

# Kickstarting with Excel

## Overview of Project
This project analyzes how different campaigns performed in relation to their launch dates and funding goals.

### Purpose
The purpose is to discover whether there is some some relationship based on these two data elements:
1) Is theatre outcome influenced by launch date?
2) Is there relation between outcomes and the goals defined for a play?

## Analysis and Challenges
The analysis was performed using the directions as specified by bootcampspot.
The only real challenge was trying to figure out how to use the COUNTIFS function in Excel.
The COUNTIFS function had to be built in pieces.
	Here is the function in the cell for "Less Than 1000"
		=COUNTIFS(Kickstarter!Q:Q,"plays",Kickstarter!F:F,"successful",Kickstarter!D:D,"<1000")
		Let's break this down:
		The sheet with the data is named Kickstarter
		The Q:Q column is the subcategory we are using in the "filter" and rows with the values "plays" is the data for which we were directed to find.
		The F:F column contains the "outcomes" which we are exploring, in this case "successful".
			We will also be searching for "failed" and "canceled" in the associated columns.
		The D:D column contains the "goal" that will be used to categorize the "goal: in a set of ranges. In this case 'Kickstarter!D:D,"<1000"' is selecting "goal" amounts less than 1000.	

	Another challenge is that the last row in the directions said to select rows with a "goal" of >50000 as seen in the formula below. 
	=COUNTIFS(Kickstarter!Q:Q,"plays",Kickstarter!F:F,"successful",Kickstarter!D:D,">50000")
	There appears to be an ERROR in the directions as we were told to pull "goal" data in these ranges:
	"45000 to 49999"
	"Greater than 50000"
	What is being left out are the rows with a "goal" of 50000, there are actually rows with this value and are being left out of the analysis. This is an ERROR in the directions.

### Analysis of Outcomes Based on Launch Date
Productions launched in April, May were the most successful and started to decline in June with a slight upticks in February and October. The "successful" and "failed" productions at the end of December actually intersect so end of December is the worst date to launch a production.

Productions that were categorized as "failed" somewhat mirror the "successful" graph but at a much diminished level. Most "failed" productions peak in May with a dramatic uptick in October. 

Productions that are categorized as "failed" peak in January bur for most if the year are flat lined, the exception being the September to first of November time frame. During the months from Septmber to early November, no productions are classified as "failed"

### Analysis of Outcomes Based on Goals
Productions with goals up to 4,999 are the most successful and then start to drop off with a dramatic drop in outcomes in the 25,000 to 29,999 range. The productions in the 40,000 to 49,999 experienced an even greater drop off in outcomes based on goal. Productions in the range 15,000 to approximately 35,000 actually had outcomes less than the failed outsomes. Then again at approximately the 42,500 goal, the outcomes were much more likely to failed instead of being a success.

### Challenges and Difficulties Encountered
There were no real difficulties encountered other the COUNTIFS function documented above in the "Analysis and Challenges" section. 

## Results

- What are two conclusions you can draw about the Outcomes based on Launch Date?
1) The most successful outcomes for productions occur in May.
2) The worst outcomes for productions happen at the end of Decmber.

- What can you conclude about the Outcomes based on Goals?
	Productions with goals up to 4,999 are the most successful and then start to drop off with a dramatic drop in outcomes in the 25,000 to 29,999 range.

- What are some limitations of this dataset?
The dates are not in a format that are readable by humans and need to go through a transformation using the function:
	=(((J2/60)/60)/24)+DATE(1970,1,1) to convert into a MM/DD/YYYY format.	

- What are some other possible tables and/or graphs that we could create?
There are several other subcategories that can be examined in a similar methodology.
