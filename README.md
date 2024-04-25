# bellabeatproject-in-gs

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

The data set contain 18 csv files. To make it easier to work with, the csv files were uploaded into Google Sheets and were batched based on the main categories (Daily Activity and Sleep) that would be useful for answering the business task questions . 

Content	Sheet
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
        
        ![MAIN RAW DATA - Google Sheets and 14 more pages - Personal - Microsoft Edge 2_28_2024 10_00_24 AM.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/9fb30c43-dc57-41f0-8b34-76ab19580b70/bec0b47c-e35c-4384-ad28-190aa972af89/MAIN_RAW_DATA_-_Google_Sheets_and_14_more_pages_-_Personal_-_Microsoft_Edge_2_28_2024_10_00_24_AM.png)
        
    - To further confirm this, I calculated the Standard deviation score using the SDEV function and this was the result: If the average step count is 8340.256112, the standard deviation remains roughly 6.14% of the average step count (512.2458225 / 8340.256112). In this context, a standard deviation that represents a small percentage of the mean may still be considered relatively low.
        
        ![MAIN RAW DATA - Google Sheets and 7 more pages - Personal - Microsoft Edge 2_29_2024 2_42_35 PM.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/9fb30c43-dc57-41f0-8b34-76ab19580b70/460cde88-a17e-4b45-b2a4-14be3c9144cb/MAIN_RAW_DATA_-_Google_Sheets_and_7_more_pages_-_Personal_-_Microsoft_Edge_2_29_2024_2_42_35_PM.png)
        
- Are there particular days where steps tend to be higher or lower?
    
    Steps tend to be higher on Saturday and Tuesday, and they tend to be lower on Sunday and Friday. 
    
    I.e people take more steps on Saturday and Tuesday and people take less steps on Sunday and Friday.
    
    ![MAIN RAW DATA - Google Sheets and 14 more pages - Personal - Microsoft Edge 2_28_2024 10_00_24 AM.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/9fb30c43-dc57-41f0-8b34-76ab19580b70/e56d5ee8-c07a-4b36-bebe-2b86084a50cb/MAIN_RAW_DATA_-_Google_Sheets_and_14_more_pages_-_Personal_-_Microsoft_Edge_2_28_2024_10_00_24_AM.png)
    
- Do users tend to take more steps on weekdays compared to weekends, or vice versa?
    
    No, there is no correlation to this as Saturday is one of the highest days for step counts while Sunday is the lowest day for step counts.
    
    ![MAIN RAW DATA - Google Sheets and 14 more pages - Personal - Microsoft Edge 2_28_2024 10_00_24 AM.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/9fb30c43-dc57-41f0-8b34-76ab19580b70/968577fa-cd95-4344-bbe1-9e511515c9a0/MAIN_RAW_DATA_-_Google_Sheets_and_14_more_pages_-_Personal_-_Microsoft_Edge_2_28_2024_10_00_24_AM.png)
    
- Are there specific times of day when users tend to burn more calories?
    
    According to this graph, people are burning most calories on Tuesday and Saturday which is to be expected as those are also the days that people take most steps on average.
    
    ![MAIN RAW DATA - Google Sheets and 14 more pages - Personal - Microsoft Edge 2_28_2024 10_07_37 AM.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/9fb30c43-dc57-41f0-8b34-76ab19580b70/1b3bd183-7e8e-4142-8f95-4d71cf822c48/MAIN_RAW_DATA_-_Google_Sheets_and_14_more_pages_-_Personal_-_Microsoft_Edge_2_28_2024_10_07_37_AM.png)
    
    However, when it came to the days people take least steps (Sundays and Fridays), people were still burning more calories than expected so I made another pivot table and created another graph to confirm that there is something going on there
    
    ![MAIN RAW DATA - Google Sheets and 5 more pages - Personal - Microsoft Edge 3_1_2024 3_58_32 PM.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/9fb30c43-dc57-41f0-8b34-76ab19580b70/f743b0e3-67da-4a90-9bc2-5823418a2c1f/MAIN_RAW_DATA_-_Google_Sheets_and_5_more_pages_-_Personal_-_Microsoft_Edge_3_1_2024_3_58_32_PM.png)
    
- Are there specific days of the week where users tend to be more active compared to others?
    
    It can be seen that users are most active during Mondays and Tuesdays, which indicates that they are usually engaging in high energy activities like running, cycling, sports etc.
    
    ALso, it can be seen that the least days are Fridays and Thursdays.
    
    ![MAIN RAW DATA - Google Sheets and 14 more pages - Personal - Microsoft Edge 2_28_2024 10_10_27 AM.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/9fb30c43-dc57-41f0-8b34-76ab19580b70/2837720a-e87a-4d63-94c8-0b67fec99ebe/MAIN_RAW_DATA_-_Google_Sheets_and_14_more_pages_-_Personal_-_Microsoft_Edge_2_28_2024_10_10_27_AM.png)
    
- How much distance, on average, do users cover each day in total and across different activity levels (very active, moderately active, light active, sedentary)?
    
    It can be found from the below that most distance (61%) is gotten from light active activities. This shows that engaging in light active distance for longer periods can lead to getting in more distance along the way.
    
    ![MAIN RAW DATA - Google Sheets and 14 more pages - Personal - Microsoft Edge 3_5_2024 10_33_08 AM.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/9fb30c43-dc57-41f0-8b34-76ab19580b70/6cf5ab4c-3757-4482-934d-fa9dbb54339d/MAIN_RAW_DATA_-_Google_Sheets_and_14_more_pages_-_Personal_-_Microsoft_Edge_3_5_2024_10_33_08_AM.png)
    
    ![MAIN RAW DATA - Google Sheets and 5 more pages - Personal - Microsoft Edge 3_1_2024 4_24_03 PM.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/9fb30c43-dc57-41f0-8b34-76ab19580b70/f3dc409c-be9f-4d8a-bb61-4382b2531330/MAIN_RAW_DATA_-_Google_Sheets_and_5_more_pages_-_Personal_-_Microsoft_Edge_3_1_2024_4_24_03_PM.png)
    
- Is there a correlation between the number of very active minutes and the total distance covered in a day?
    
    Yes, there is a high correlation between the very active minutes and the total distance. This means that users engage in sports that are high intensity and cover lots of distance eg running, cycling, hiking etc.
    
    ![A summary of your analysis and 5 more pages - Personal - Microsoft Edge 3_1_2024 4_30_00 PM.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/9fb30c43-dc57-41f0-8b34-76ab19580b70/58c4b269-bfa4-4874-91c1-f582492120ab/A_summary_of_your_analysis_and_5_more_pages_-_Personal_-_Microsoft_Edge_3_1_2024_4_30_00_PM.png)
    
    ![A summary of your analysis and 5 more pages - Personal - Microsoft Edge 3_1_2024 4_31_31 PM.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/9fb30c43-dc57-41f0-8b34-76ab19580b70/a91df62b-f6de-4257-bc7a-d48ef533b40f/A_summary_of_your_analysis_and_5_more_pages_-_Personal_-_Microsoft_Edge_3_1_2024_4_31_31_PM.png)
    
- What's the relationship between steps taken in a day and sedentary minutes?
    
    - Steps/ Sedentary Minutes: There was a very slight downward slope, which indicates no correlation between the two
        
        ![MAIN RAW DATA - Google Sheets and 6 more pages - Personal - Microsoft Edge 3_4_2024 9_44_52 AM.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/9fb30c43-dc57-41f0-8b34-76ab19580b70/dec6c39e-f2d0-42ce-b678-288d909d5b66/MAIN_RAW_DATA_-_Google_Sheets_and_6_more_pages_-_Personal_-_Microsoft_Edge_3_4_2024_9_44_52_AM.png)
        
    - Steps/ Very Active Minutes: There was a high upward slope, which indicates high correlation between the two
        
        ![MAIN RAW DATA - Google Sheets and 6 more pages - Personal - Microsoft Edge 3_4_2024 9_43_49 AM.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/9fb30c43-dc57-41f0-8b34-76ab19580b70/7b22ed4d-4e2b-4f28-b7ef-e69a7194ada6/MAIN_RAW_DATA_-_Google_Sheets_and_6_more_pages_-_Personal_-_Microsoft_Edge_3_4_2024_9_43_49_AM.png)
        
    - Steps/ Calories: There was a very moderate upward slope, which indicates moderate correlation between the two
        
        ![MAIN RAW DATA - Google Sheets and 6 more pages - Personal - Microsoft Edge 3_4_2024 9_42_58 AM.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/9fb30c43-dc57-41f0-8b34-76ab19580b70/6c849a57-3017-4038-b79a-7a0c4083ee58/MAIN_RAW_DATA_-_Google_Sheets_and_6_more_pages_-_Personal_-_Microsoft_Edge_3_4_2024_9_42_58_AM.png)
        
- Is there a relationship between sedentary minutes and overall daily calorie burn?
    
    There is little to no relationship as the trendline is considerably flat.
    
    ![MAIN RAW DATA - Google Sheets and 6 more pages - Personal - Microsoft Edge 3_4_2024 9_02_04 AM.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/9fb30c43-dc57-41f0-8b34-76ab19580b70/3ea6b83b-9559-40df-83bd-696499fabb1b/MAIN_RAW_DATA_-_Google_Sheets_and_6_more_pages_-_Personal_-_Microsoft_Edge_3_4_2024_9_02_04_AM.png)
    
- Any correlation between total steps and total calories burned?
    
    There is considerable correlation as the trendline is slanted to a good amount
    
    ![MAIN RAW DATA - Google Sheets and 6 more pages - Personal - Microsoft Edge 3_4_2024 9_03_47 AM.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/9fb30c43-dc57-41f0-8b34-76ab19580b70/bb8822b2-4c79-49b8-a5a8-3e499be8ba55/MAIN_RAW_DATA_-_Google_Sheets_and_6_more_pages_-_Personal_-_Microsoft_Edge_3_4_2024_9_03_47_AM.png)
    
- What is the percentage of users that log activities they engage in?
    
    89% of users don't track their activities while 11% of users do. 
    
    Users who track their activities have 77% of the very active minutes and users who don't track have 23% of the very active minutes. 
    
    Users who track their activities have 47.6 % of the sedentary minutes and users who don't track have 52.4% of the sedentary minutes.

  ## Key Findings and Supporting Visuals

  - **Key Finding #1**
    - *How consistent are step counts throughout the week?*
    - The step counts throughout the week show relative consistency, with a 17% difference between the minimum average count (Sunday) and the maximum average count (Tuesday). Additionally, the standard deviation remains approximately 6.14% of the mean step count, indicating relatively low variability
        
        ![Step Count Trends Across Days of the Week.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/9fb30c43-dc57-41f0-8b34-76ab19580b70/34767118-e8c3-4f88-970f-a4d0521c303b/Step_Count_Trends_Across_Days_of_the_Week.png)
        

---

- **Key Finding #2**
    - *Are there specific days of the week where users tend to be more active compared to others?*
    - Users tend to be most active on Mondays and Tuesdays, when they’re likely to be engaging in high-energy activities like running, cycling, sports, e.t.c at the start of the week, while towards the end of the week, Thursdays and Fridays are observed to be the least active days.
    
    ![Exploring User Activity_ Peak Days Through the Week.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/9fb30c43-dc57-41f0-8b34-76ab19580b70/1c062387-cf1e-4ea6-958a-0cc4d063b879/Exploring_User_Activity__Peak_Days_Through_the_Week.png)
    

---

- **Key Finding #3**
    - *How much distance, on average, do users cover each day in total and across different activity levels (very active, moderately active, light active, sedentary)?*
    - A significant portion (61%) of the total daily distance covered stems from low-intensity physical activities, including walking, household chores, and light recreational activities, emphasizing their importance in daily activity levels."
    
    ![Understanding User Activity_ Average Daily Distance Across Activity Levels.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/9fb30c43-dc57-41f0-8b34-76ab19580b70/b5752810-4268-461f-a313-001bee970070/Understanding_User_Activity__Average_Daily_Distance_Across_Activity_Levels.png)
    

---

- **Key Finding #4**
    - *Is there a correlation between the number of very active minutes and the total distance covered?*
    - A positive correlation exists between very active minutes and total distance covered, indicating that users engage in high-intensity sports activities such as running, cycling, and hiking, leading to significant distances covered on a daily basis.
    
    ![Understanding Activity Patterns (1).png](https://prod-files-secure.s3.us-west-2.amazonaws.com/9fb30c43-dc57-41f0-8b34-76ab19580b70/f4a9df9f-7384-41d3-bbec-33bfa73c5b62/Understanding_Activity_Patterns_(1).png)
    

---

- **Key Finding #5**
    - *What is the percentage of users that log activities they engage in?*
    - The majority of users (89%) do not track their activities, while a minority (11%) do. Users who track activities contribute significantly more to very active minutes (77%) and less to sedentary minutes (47.6%) compared to non-trackers.
    
    ![Distribution of Activity Tracking Behavior Among Users (1).png](https://prod-files-secure.s3.us-west-2.amazonaws.com/9fb30c43-dc57-41f0-8b34-76ab19580b70/30cd6287-dc52-4a22-b00e-108dbcdf61dc/Distribution_of_Activity_Tracking_Behavior_Among_Users_(1).png)
    
    ![Exploring User Behavior_ Activity Level and Tracking.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/9fb30c43-dc57-41f0-8b34-76ab19580b70/3ee272f3-e4ff-4b26-9adc-c0ba1b9962a2/Exploring_User_Behavior__Activity_Level_and_Tracking.png)
    
    ![Exploring User Behavior_ Activity Level and Tracking (1).png](https://prod-files-secure.s3.us-west-2.amazonaws.com/9fb30c43-dc57-41f0-8b34-76ab19580b70/60aa0d22-787d-4f6e-9496-c0041abb127d/Exploring_User_Behavior__Activity_Level_and_Tracking_(1).png)
    
    ![Exploring User Behavior_ Activity Tracking and Calories Burnt.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/9fb30c43-dc57-41f0-8b34-76ab19580b70/c2ed2a67-b409-4774-958a-ea8d1faf6d72/Exploring_User_Behavior__Activity_Tracking_and_Calories_Burnt.png)


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

  
