# bellabeatproject-in-gs

[Presentation Document - Project Overview, Key Findings + Supporting Visualizations and Recommendations](https://docs.google.com/presentation/d/1gT5MjjK4A1MqUjy77pXBKkfyfiGvs6TzaPtz2egr1JI/edit#slide=id.g2c43ea45db0_0_107)

## A Clear Summary of the Business Task
**The business task of this project is** 

- to analyze the trends in smart device usage data and use that to gain insights into consumer usage behavior and give recommendations for the marketing strategy of the Bellabeat app based on the insights.

**The key stakeholders are as follows:** 

- Urška Sršen: Bellabeat’s cofounder and Chief Creative Officer
- Sando Mur: Mathematician and Bellabeat’s cofounder; key member of the Bellabeat executive team

The secondary stakeholders are as follows:

- the Bellabeat marketing analytics team.

- **Guiding Questions for the Analysis**

These questions provide insights into overall step and activity levels, their patterns throughout the week, and how activity levels relate to calorie burn and sedentary behavior. They serve as a foundation for understanding user behavior and informing marketing strategies for Bellabeat products.

- How consistent are step counts throughout the week? Are there particular days where steps tend to be higher or lower? Do users tend to take more steps on weekdays compared to weekends, or vice versa?


## A Description of All Data Sources Used

### Data Source Overview

The data source used is the FitBit Fitness Tracker Data, which was uploaded to Kaggle by Mobius under the CC0 Public Domain License. 

The data was gathered through a survey on the Amazon Mechanical Turk Platform, and thirty eligible Fitbit users consented to the submission of personal tracker data, including minute, hourly and daily level output for their physical activity, heart rate, and sleep monitoring. 

### Data Source Details

The data set contain 18 csv files. To make it easier to work with, the csv files were uploaded into Google Sheets and were batched based on the main category (Daily Activity) that would be useful for answering the business task questions . 

#### Raw Daily Activity Data - Google Sheets
Id, ActivityDate, TotalSteps, TotalDistance, TrackerDistance, LoggedActivities, Distance, VeryActiveDistance, ModeratelyActiveDistance, LightActiveDistance, SedentaryActiveDistance, VeryActiveMinutes, FairlyActiveMinutes, LightlyActiveMinutes, SedentaryMinutes, Calories	Raw Daily Activity Data - Google Sheets


### Data’s Integrity

The data was thoroughly checked for accuracy, completeness, consistency, and trustworthiness of data throughout its lifecycle. The following are findings that were derived:

- The data is relevant to the business task and sufficient details are in the data
- The privacy of the respondents have been preserved through the use of only ID numbers and the absence of any PII ( Personally identifiable information)
- Using pivot tables to get an overview of the data, a few inconsistencies were noticed with the entries on some days.
- A lot of attributes had ‘0’ entries
- No duplicate rows were found.
- 33 users IDs were logged as opposed to the 30 users that were acclaimed. This means that user/s probably created a user id more than once.
    - *Margin of Error Check Score -* 
    **15.07%** with a population size of **55M,** a confidence level of **90%** and a sample size of **30.**
    *Click the toggle for more details*
        - Since we already have the survey data to work with, I made use of the margin of error calculator to determine how much our results with the survey data is going to differ from the actual results we would get if we are to use data from the total population
        - The estimated number of people using smart health devices is 10M - 100M according to ChatGPT. I went with the middle number for the calculation i,e 55 million.
        

### Limitations of the Data

Limitations of the data are as follows: 

- the sample size is considerably low
- Lack of qualitative data (No demographic attributes were included)
- The one-month time frame is considerably low and the data might not be a proper representation of day to day usage over a long period of time
- There is a significant number of unlikely inputs in the data like very low hours of sleep / zero steps in a day.
- Are there specific times of day when users tend to burn more calories? Are there specific days of the week where users tend to be more active compared to others? How much distance, on average, do users cover each day in total and across different activity levels (very active, moderately active, light active, sedentary)? Is there a correlation between the number of very active minutes and the total distance covered in a day? Are there particular times of the day when users are more active or sedentary? Is there a relationship between sedentary minutes and overall daily calorie burn?

## Documentation of Any Cleaning or Manipulation of Data
### **Introduction**

The data source used is the FitBit Fitness Tracker Data, that was gathered through a survey on the Amazon Mechanical Turk Platform, and thirty eligible Fitbit users consented to the submission of personal tracker data, including minute, hourly and daily level output for their physical activity, heart rate, and sleep monitoring. 

### Data Cleaning Objectives

The objectives of the data cleaning process at this stage are as follows:

1. **Handling Missing Values**: Address missing data in fields like steps, distance, heart rate, and duration.
2. **Removing Duplicates**: Eliminate duplicate entries to ensure each observation is unique.
3. **Standardizing Data Formats**: Ensure consistency in date formats, units, and data representation.
4. **Correcting Errors and Inconsistencies**: Rectify data entry errors, outliers, and inconsistencies.
5. **Handling Outliers**: Address outliers while maintaining dataset integrity.
6. **Ensuring Data Quality and Reliability**: Assess and improve data quality standards.
7. **Documentation and Traceability**: Document cleaning procedures and outcomes for transparency.

### Data Cleaning Steps

**Step 1: Data Exploration and Assessment**

- Used a pivot table to get an overview of the data.
- Used the sort and filter functions to get a better understanding of the data.
- Checked the data’s margin of error score to determine the reliability of the data set.
- Checked the data for wrong spellings, wrong data formats, blank spaces/nulls, duplicates, inconsistent field length, outliers etc.
- Created a copy of the data set first before any manipulation to the data was done.

**Step 2: Handling Missing Values**

- Used a pivot table to check the number of entries for each ID. THE ID number “4057192912” had only 4 entries so the entries were removed to maintain the integrity and quality of the data set.
- Using the pivot table again, the number of entries including 0, in the Total Steps and Total Activity section were 76 entries.  The entries were removed to maintain the integrity and quality of the data set. For further clarification, the entries that had null values were the same with the total steps so they cancelled each other out
- Also, to ensure I wasn’t making too much of a drastic change to the data set, I plotted graphs with the two data sets and there was no difference between the original data set and the data set with the nulls removed.
    

**Step 3: Removing Duplicates**

- Used the remove duplicates tool to search for and remove duplicates. No duplicates were found in the data set.

**Step 4: Standardizing Formats**

- Noticed the ID numbers were formatted wrongly so I copied and pasted the column and it came out well.

**Step 6: Handling Outliers**

- The data was plotted into a bar graph to check for outliers and extremely comparably low values were found in the total steps and total distance. This is due to the cells with null values that are present in the data.

**Step 7: Addressing Inconsistencies**

- The data was checked for inconsistencies in categorical variables or labels and there were none, ensuring uniformity and accuracy in the data.
- Verified the length of the primary key (ID number) by using the LEN function to determine the length of each ID number. Then I used the COUNTIF function to verify that all the numbers are the same length

**Step 8: Verifying Data Integrity**

- *Margin of Error Check Score -* 
**15.07%** with a population size of **55M,** a confidence level of **90%** and a sample size of **30.**
*Click the toggle for more details*
    - Since we already have the survey data to work with, I made use of the margin of error calculator to determine how much our results with the survey data is going to differ from the actual results we would get if we are to use data from the total population
    - The estimated number of people using smart health devices is 10M - 100M according to ChatGPT. I went with the middle number for the calculation i,e 55 million
    

### Tools and Techniques Used

- Margin of Error Calculator
- Pivot table
- Sort function
- Filter function
- Remove duplicates tool
- Data visualization tool (Bar Graph)
- LEN function
- COUNTIF Function

### **Documentation of Changes**

- [x]  Created a copy of the data set
- [x]  Used remove duplicates tool
    
    No duplicates were found
    
- [x]  Removed ‘irrelevant data
Not needed
- [x]  Removed extra spaces and blanks (TRIM function)
    
    Didn’t need this as the data set doesnt have qualitative data
    
- [ ]  Fixed misspellings (Spell Check, Autocorrect and conditional formatting)
    
    Didn’t need this as the data set doesnt have qualitative data
    
- [ ]  Fixed inconsistent capitalization (UPPER, LOWER, PROPER)
    
    Didn’t need this as the data set doesnt have qualitative data
    
- [x]  Removed formatting (Clear formatting)
    
    Noticed the ID numbers were formatted wrongly so I copied and pasted the column and it came out well.
    
- [ ]  Incorrect Punctation and other Typos
    
    Didn’t need this as the data set doesnt have qualitative data
    
- [ ]  Check and remove inconsistent data (COUNITF, LEN, PIVOT TABLES)
    
    Verified the length of the primary key (ID number) by using the LEN function to determine the length of each ID number. Then I used the COUNTIF function to verify that all the numbers are the same length
    
    Used a pivot table to check the number of entries for each ID. THE ID number “4057192912” had only 4 entries so the entries were removed to maintain the integrity and quality of the data set. 
    
    Using the pivot table again, the number of entries including 0, in the Total Steps and Total Activity section were 76 entries.  The entries were removed to maintain the integrity and quality of the data set. For further clarification, the entries that had null values were the same with the total steps so they cancelled each other out
    
    Also, to ensure I wasn’t making too much of a drastic change to the data set, I plotted graphs with the two data sets and there was no difference between the orginal data set and the data set with the nulls removed.
    
        
- [ ]  Clean data strings (LEFT, RIGHT, MID, CONCATENATE
    
    Didn’t need this as the data set doesnt have qualitative data
    
- [x]  Check data for outliers
    
    The data was plotted into a bar graph to check for outliers and extremely comparably low values were found in the total steps and total distance. This is probably due to the null cells that are present in the data. 
    

### **Summary and Conclusions**

The dataset has undergone thorough review and is now ready for analysis. Missing values were addressed, data formats were standardized, and duplicates were removed. Outliers were carefully handled, and data integrity was verified. Documentation was updated for transparency.

In conclusion, the dataset is clean, consistent, and reliable, setting the stage for meaningful analysis and informed decision-making.


## A Summary of Analysis
### Business Task Questions

- How consistent are step counts throughout the week?
    - The step counts are fairly consistent as there is a 17% difference from the minimum average step count (Sunday) and the maximum average step count (Tuesday).
        
        
    - To further confirm this, I calculated the Standard deviation score using the SDEV function and this was the result: If the average step count is 8340.256112, the standard deviation remains roughly 6.14% of the average step count (512.2458225 / 8340.256112). In this context, a standard deviation that represents a small percentage of the mean may still be considered relatively low.
        
        
- Are there particular days where steps tend to be higher or lower?
    
    Steps tend to be higher on Saturday and Tuesday, and they tend to be lower on Sunday and Friday. 
    
    I.e people take more steps on Saturday and Tuesday and people take less steps on Sunday and Friday.
    
- Do users tend to take more steps on weekdays compared to weekends, or vice versa?
    
    No, there is no correlation to this as Saturday is one of the highest days for step counts while Sunday is the lowest day for step counts.
    

- Are there specific times of day when users tend to burn more calories?
    
    According to this graph, people are burning most calories on Tuesday and Saturday which is to be expected as those are also the days that people take most steps on average.
    
    
    However, when it came to the days people take least steps (Sundays and Fridays), people were still burning more calories than expected so I made another pivot table and created another graph to confirm that there is something going on there
    
    
- Are there specific days of the week where users tend to be more active compared to others?
    
    It can be seen that users are most active during Mondays and Tuesdays, which indicates that they are usually engaging in high energy activities like running, cycling, sports etc.
    
    ALso, it can be seen that the least days are Fridays and Thursdays.
    
    
- How much distance, on average, do users cover each day in total and across different activity levels (very active, moderately active, light active, sedentary)?
    
    It can be found from the below that most distance (61%) is gotten from light active activities. This shows that engaging in light active distance for longer periods can lead to getting in more distance along the way.
    
    
- Is there a correlation between the number of very active minutes and the total distance covered in a day?
    
    Yes, there is a high correlation between the very active minutes and the total distance. This means that users engage in sports that are high intensity and cover lots of distance eg running, cycling, hiking etc.
    
    
- What's the relationship between steps taken in a day and sedentary minutes?
    
    - Steps/ Sedentary Minutes: There was a very slight downward slope, which indicates no correlation between the two
        
        
    - Steps/ Very Active Minutes: There was a high upward slope, which indicates high correlation between the two
        
        
    - Steps/ Calories: There was a very moderate upward slope, which indicates moderate correlation between the two
        
        
- Is there a relationship between sedentary minutes and overall daily calorie burn?
    
    There is little to no relationship as the trendline is considerably flat.
    
- Any correlation between total steps and total calories burned?
    
    There is considerable correlation as the trendline is slanted to a good amount
    
    
- What is the percentage of users that log activities they engage in?
    
    89% of users don't track their activities while 11% of users do. 
    
    Users who track their activities have 77% of the very active minutes and users who don't track have 23% of the very active minutes. 
    
    Users who track their activities have 47.6 % of the sedentary minutes and users who don't track have 52.4% of the sedentary minutes.

  ## Key Findings and Supporting Visuals

  - **Key Finding #1**
    - *How consistent are step counts throughout the week?*
    - The step counts throughout the week show relative consistency, with a 17% difference between the minimum average count (Sunday) and the maximum average count (Tuesday). Additionally, the standard deviation remains approximately 6.14% of the mean step count, indicating relatively low variability
        

---

- **Key Finding #2**
    - *Are there specific days of the week where users tend to be more active compared to others?*
    - Users tend to be most active on Mondays and Tuesdays, when they’re likely to be engaging in high-energy activities like running, cycling, sports, e.t.c at the start of the week, while towards the end of the week, Thursdays and Fridays are observed to be the least active days.
    
  
---

- **Key Finding #3**
    - *How much distance, on average, do users cover each day in total and across different activity levels (very active, moderately active, light active, sedentary)?*
    - A significant portion (61%) of the total daily distance covered stems from low-intensity physical activities, including walking, household chores, and light recreational activities, emphasizing their importance in daily activity levels."
    

---

- **Key Finding #4**
    - *Is there a correlation between the number of very active minutes and the total distance covered?*
    - A positive correlation exists between very active minutes and total distance covered, indicating that users engage in high-intensity sports activities such as running, cycling, and hiking, leading to significant distances covered on a daily basis.
    

---

- **Key Finding #5**
    - *What is the percentage of users that log activities they engage in?*
    - The majority of users (89%) do not track their activities, while a minority (11%) do. Users who track activities contribute significantly more to very active minutes (77%) and less to sedentary minutes (47.6%) compared to non-trackers.


  ## Top Level Insights Based on Analysis

  - **Recommendation #1 - Maximize Activity Levels throughout the Week**
To capitalize on peak activity levels observed on Mondays and Tuesdays, 
1. Tailored content and challenges can be designed to align with users' heightened motivation at the start of the week. 
2. Midweek incentives and exclusive content can help to sustain momentum beyond Mondays and Tuesdays. 
3. Promote wellness activities on Thursdays and Fridays can support users' relaxation and recovery needs during quieter periods. 
    

- **Recommendation #2 - Leverage Users’ Engagement in Low-Intensity Physical Activities**
To leverage the users’ engagement in low-intensity physical activities
1. Offer a variety of low-activity options, such as guided walks and stretching routines on the app. 
2. Help users to set achievable distance goals tailored to users' current fitness levels, breaking larger goals into manageable milestones to foster a sense of progress.


- **Recommendation #3 - Leverage Users’ Patterns of High Distance Exercise with Endurance Training**
1. Promote and diversify physical activities that involve movement over distance, such as running, cycling, hiking, or brisk walking, by providing advanced training programs, personalized plans, and access to specialized resources. 
2. Offer features that track and visualize performance metrics related to high distance and high-intensity activities, such as pace, elevation gain, or heart rate zones, to help users optimize their training, understand the impact of their efforts and progress towards their fitness goals more effectively.
        

- **Recommendation #4 - Improve User Interaction with Optimization of the Activity Tracking Experience
1.** Encourage users to track their activity levels by promoting the benefits of activity monitoring, such as increased awareness and progress towards fitness goals. 
2. Incentivize regular activity logging through rewards programs (virtual badges, achievement milestones, or exclusive content) engaging challenges. 
3. Customize the user experience by allowing flexibility in tracking options, such as manual entry, automatic tracking via connected devices, or integration with third-party fitness apps, to cater to individual preferences and goals. 
4. Automatic activity detection can be implemented to reduce friction between tracking devices.
  

- **Recommendation #5 -Encourage Healthier Lifestyle for Users through Demystifying Activity Tracking and Its Benefits
1.** Promote activity tracking as an essential component of users' daily routines, emphasizing its role in increasing awareness of physical activity levels and more active lifestyles. 
2. Develop user-friendly tutorials, guides, and interactive tools to demystify the process of tracking activities and navigating related metrics, to understand the impact of their daily tracking on their activity levels.

  
