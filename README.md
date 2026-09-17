# ECE-2112-Advanced-Computer-Programming-and-Algorithms-Programming-Assignment-4-
My Programming Assignment #4 for my ECE 2112: Advanced Computer Programming and Algorithms, which includes the uses and applications of the lessons attained from Module #4

import pandas as pd - Imports the pandas Library into the compiler and renames it as a function pd

import matplotlib.pyplot as plt - Imports the Matplotlib Library into the compiler and renames it as a function plt

A. VISAYAS COMMUNICATION DATAFRAME

1. df = pd.read_excel('board2.xlsx') - The line of code that reads the Excel file provided for the assignment named board2.xlsx

2. df['Average'] = df[['Math', 'Electronics', 'GEAS', 'Communication']].mean(axis = 1)

  2a. df['Average'] - The line of code that creates a new column on the dataframe named 'Average'

  2b. df[['Math', 'Electronics', 'GEAS', 'Communication']].mean(axis = 1) - The line of code that obtains the columns: Math, Electronics, GEAS, and Communication while getting the mean of their axis 1, essentially getting the mean of each row

3. VisComm= df.loc[(df['Hometown'] == 'Visayas')&(df["Track"] == 'Communication'), ['Name', 'Gender', 'Math', 'Electronics','Average']]

  3a. df.loc[(df['Hometown'] == 'Visayas') - This line of code creates a condition that in the dataframe df, only the rows with their hometown being Visayas are saved

  3b. (df["Track"] == 'Communication') - this line of code creates an additional condition that takes the rows that have their Track as Communication. 

4. len(VisComm) - Obtains the length of the VisComm dataframe, counting only the rows


B. VISAYAS FEMALE DATAFRAME

1. VisFemale = df.loc[(df['Hometown'] == "Visayas") & (df['Gender'] == 'Female')][['Name', 'Track', 'GEAS', 'Electronics', 'Average']]

  1a. df.loc[(df['Hometown'] == "Visayas") - The line of code that has the condition that obtains all of the rows with Visayas

  1b. (df['Gender'] == 'Female')] - a secondary condition obtaining all rows that fulfill the boolean condition of the Gender Column equating to Female

  1c. [['Name', 'Track', 'GEAS', 'Electronics', 'Average']] - The portion of the code that sections off the columns, instructed

2. VisFemale[VisFemale['Average']>=60] - The line of Code that uses the Boolean conditioning that displays only to the rows in VisFemale that have an Average of greater than or equal to 60.


C. CATEGORY-AVERAGE VISUALIZATION

1. track_mean = df.groupby('Track')['Average'].mean() - The line of code that groups the subgroups of the Column "Track" and gets the mean of each subgroup, respectively.

2. gender_mean = df.groupby('Gender')['Average'].mean() - The line of code that groups the subgroups of the Column "Gender" and gets the mean of each subgroup, respectively.

3. hometown_mean = df.groupby('Hometown')['Average'].mean() - The line of code that groups the subgroups of the Column "Hometown" and gets the mean of each subgroup, respectively.

4. fig, axes = plt.subplots(1, 3, figsize=(15, 5)) -

   4a. fig, axes - The variable name

   4b. axes - the portion of code that holds the chart areas

   4c. plt.subplots - Creates a grid with subplots

   4d. (1,3, figsize=(15, 5)) - creates the grid with 1 row and 3 columns, while having the entire grid have a width of 15 and height of 5. 

   4e. axes[0].bar(track_mean.index, track_mean.values) - The setup of the first bar graph in the [0] index area of the grid, while indicating the track_mean.index as the x-axis and the track_mean.values as the y-axis

   4f. axes[0].set_title('Mean Average by Track') - This portion creates the title of the chart 

   4g. axes[0].set_xlabel('Track') - Labels the x-axis with the title of Track

   4h. axes[0].set_ylabel('Mean Average') - Labels the y-axis with the title of Mean Average

   4i. axes[1].bar(gender_mean.index, gender_mean.values) - The setup portion of the second bar graph in the [1] index of the grid, while indicating gender_mean.index as the x-axis and the gender_mean.values as the y-axis

   4j. axes[1].set_title('Mean Average by Gender') - Creates the title of the second chart 

   4k. axes[1].set_xlabel('Gender') - Labels the x-axis with the title of Gender

   4l. axes[1].set_ylabel('Mean Average') - Labels the y-axis with the title of Mean Average

   4m. axes[2].bar(hometown_mean.index, hometown_mean.values) - The setup portion of the third bar graph in the [2] index of the grid, while indicating hometown_mean.index as the x-axis and the hometown_mean.values as the y-axis

   4n. axes[2].set_title('Mean Average by Hometown') - Labels the title of the third chart 

   4o. axes[2].set_xlabel('Hometown') - Labels the x-axis with the title of Hometown

   4p. axes[2].set_ylabel('Mean Average') -  Labels the y-axis with the title of Mean Average

   4q. plt.tight_layout() - a sort of automatic function that polishes the created layout 

   4r. plt.show() - displays the figure

5. print("Track:",    track_mean.sort_values(ascending=False).index[0],    "has the highest mean Average.")
 
print("Gender:",   gender_mean.sort_values(ascending=False).index[0],   "has the highest mean Average.")

print("Hometown:", hometown_mean.sort_values(ascending=False).index[0], "has the highest mean Average.") - The entire code uses the same logic of acquiring the feature_mean, and then using the .sort_values() function with the condition of ascending=False which is a way of sorting it in an descending order, then if we can obtain the highest Average or Number, by acquiring the Index[0] which is the high number after sorting. 









