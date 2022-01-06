## Longitudinal Impact Report for the UMD Alumni Association

### 1. Introduction

This is a Longitudinal Impact Report providing valuable insights to the Univeristy of Maryland Alumni Association in order to streamline their future events regarding increasing the number of first-time attendees and major gift prospects.

### 2. Requirements

For the working of the project, the following packages are used:
-	**Pandas** <br>
It is a high-performance, easy-to-use data structures, and analysis tool. Pandas makes it simple to do many of the time-consuming, repetitive tasks associated with working with data.
-	**Seaborn** <br>
Seaborn is an open-source Python library built on top of matplotlib. It is used for data visualization and exploratory data analysis. Seaborn works easily with dataframes and the Pandas library. The graphs created can also be customized easily as per user convenience and likings.
-	**NumPy** <br>
NumPy is a package majorly used for scientific computing in python. It is a very powerful library used for working with arrays.
-	**Matplotlib** <br>
Matrix Plot Library or Matplotlib is a data visualization and graphical plotting library for Python language and its numerical extension NumPy.

### 3. Platforms Used
We have used Google Colab and Jupyter Notebook to carry out the coding and testing of the project.

### 4. Analysis of the Code

The following section provides an in-depth explanation of each section of the code used and the corresponding output it generates, along with the insights gained.


Data import and description for the database:

- We used the concat() function to combine the excel sheets for all the years into one data frame. This helps us to analyze the data easily and execute the commands on the entire data.
-	We used the describe() function to display the summary statistics of the data frame. It provides us with the basic yet important dataframe statistics like the mean, median, different quartile ranges, etc.
-	We used the is.null() function to check whether there are any null values in any of the columns of the dataframe. This helps us to analyze whether we need to perform any form of data cleansing.
-	Also, we used the dataframe.duplicated() function to check whether there are any duplicate line entries in any of the rows of the dataframe. The function value_counts() is used to give us the total count of the output of the duplicated() function.
-	Imported the Pandas Profiling Library which generates a profile report of the dataframe. It provides us with the initial direction to approach our project. It is an open-source library used to perform exploratory data analysis. It generates user-friendly, interactive reports in a web format and shows the interaction between different variables. We can easily switch between different variables of the dataframe and obtain the scatter plots, correlation plots between them. We can also obtain summary statistics on each variable.
For initiating the Pandas Profiling method, we need to first run the following code on the command prompt to install the pip package manager:
```
pip install -U pandas-profiling[notebook]
jupyter nbextension enable --py widgetsnbextension
```

-	We used the dataframe.corr() function to find the pairwise correlation of all numeric columns in the dataframe. Any NA values are automatically excluded. The following table is obtained:

![](https://ppt.cc/fugkRx@.png)

The correlation table provides us with helpful insights as to which particular columns are highly related to each other. The columns with high correlation       values become our target variables for the course of the project along with some other non-numerical columns analysed further.

-	We used the sns.heatmap() function to show a generalized view of the numeric values, which are represented in shaded colors. It shows us the correlation between 2 sets of attributes in the form of a matrix. It helped us in finding patterns and gaining perspective as to which attributes to focus on. 
 
![](https://ppt.cc/fCX4Jx@.png)

After analyzing the heat map, we can see which attributes have the maximum correlation and perform further analysis on those attributes. For example, we can see that the percentage of major prospects is considerably correlated to the average age of an attendee. 
-	The following steps are used for creating various bar charts in the project. First we assign the x-axis labels to a variable x_indexes which is then used in the ax.bar function(). The size of the plots was defined using the figsize function. The ax.bar is used to plot the bar positioned at x_indexes. Their dimensions are given by width and height if required. A label can also be added. Regarding the colour of the plots, we chose to depict data related to First Time Attendees with a golden colour of hex code #fdb515, and the Major Prospects with a maroon colour of hex code #872828. The title and axis labels are set based on the content of the plot. The tick location of x and y-axis is set using the set_xticks and set_yticks functions. Different scale of % values is used on the y-axis of each plot in order to provide better visualization, since the output of different plots will be differently sized. To label each bar with the corresponding % value, a for-loop is used to iterate through the number of ticks to be displayed, and axes.text() function is used to set the label to be displayed along with the position and font size.

#### Analyzing the Location Code <br>
-	We initiated a for loop and checked the second digit of the Location Code and turned them into categorical values to receive the location where the event was held and divided it into 5 categories.
-	Assigned each category a column in a new data frame ‘Location Group’
-	We used the groupby function to find the total number of participants, total number of first-time attendees and major prospects in each location. 
-	We then find the percentage for the first-time attendees and major prospects for each location. 
-	Created bar charts for visualizations and inferred that 36% of the first-time attendees preferred the events held in the location Southeast and 35% of the first time attendees were attracted to Online events whereas locations in Southeast and Northeast appeal to 23% and 20% of the major prospects respectively.

#### Analyzing the Group Code – Events’ Audience 
-	We initiated a for loop and checked the third digit of the Group Code and turned them into categorical values to receive the category of the group 
-	Assigned each of the 5 categories a column in a new data frame ‘Group’
-	Used the groupby function to find the total number of participants, total number of first-time attendees and major prospects in each group.
-	We then find the percentage for the first-time attendees and major prospects for each group. 
-	Created bar charts for visualizations and found that 47% of the first-time attendees are Students & Alumni whereas the 18% of the major prospects are Members. 

#### Analyzing the Group Code – Events’ Purpose
-	We initiated a for loop and checked the second digit of Group Code and turned them into categorical values to receive the event contents of the group.
-	Assigned each of the 7 types a column in a new data frame ‘Group Contents’
-	Used the groupby function to find the total number of participants, total number of first-time attendees and major prospects in each type of group content. 
-	We then find the percentage for the first-time attendees and major prospects for each type of group content. 
-	Created bar charts for visualizations and found that 27% of the major prospects prefer the groups with ‘Stewardship’ content and 34% of the first-time attendees prefer the groups with ‘Social’ content. 

#### Analyzing Activity Code
-	We grouped the Activity Code and calculated the number of first time attendees and major prospects to obtain each activity’s popularity. 
-	Created bar charts for the number of first-time attendees and major prospects for each Activity Code
-	We found that the maximum number of first-time attendees have attended the events with the activity PEZGB which is GradBash, whereas the maximum number of major prospects have attended the events with the activity PEZMM which is Maryland at Manhattan. 

#### Analyzing the Age
-	We sub-categorized the average age into five groups (under 30, 30-39, 40-49, 50-59 and over 60) and named the column "Age Group".
-	We used the groupby function to find the total number of first-time attendees and major prospects in each age group.
-	We then found the percentage for the first-time attendees and major prospects for each age group by calculating the number of people attending for the first time divided by the number of people participating in total. Similar calculations are done for the percentage of major prospects.
-	Created bar charts for visualizations and found that the maximum percentage of first-time attendees are under the age of 30 which was very much on expected lines since recent graduates and young people are bound to attend more events. However, the age group of under 30 contributed next to 0% of them being the major prospects.  The maximum percentage of major prospects are people in the Over 60 age group.
-	We used the sns.pairplot() to plot pairwise relationships of the dataset based on the age groups. The histogram shows us the distribution of a single variable, whereas the scatter plots show us the relation between different variables in terms of the age group. 

![](https://ppt.cc/fco8qx@.png)

#### Analyzing the Event Date – Day
-	Applied dt.weekday to extract the number of weekdays for the event.
-	Using a for loop, we transformed the number of weekdays each event was held into texts. For example, if the number is 0, we call it Mon.(Monday). Then we created a new column for the data.
-	Using the groupby function, we calculated the total number of first time attendees,major prospects, and participants. By dividing the number of participants, we can get the percentage of first-time attendees and major prospects for weekdays and weekends separately and use bar graphs for visualization. We further conclude that the major prospects and first-time attendees prefer attending the events held on weekends.  
-	We calculated these percentages for each day of the week as well and found that 40% of the first-time attendees prefer the events on Mondays, whereas 19% of the major prospects prefer the events held on Fridays. 

#### Analyzing the Event Date – Month
-	Applied dt.month to extract the month for the event.
-	Using the groupby function, we calculated the total number of first time attendees,major prospects, and participants for each month. By dividing the number of participants, we can get the percentage of first-time attendees and major prospects for each month separately and use bar graphs for visualization. 
-	Using bar graphs for visualization, we conclude that there are 3 peaks for the percentage of first time attendees, which are events that are held in May (42%), July (38%), and September (38%). For major prospects, the top two percentages are the events being held in September (19%) and December (18%). 

#### Regression Model
-	We created two explanatory regression models to find which variable has the effects on our targets and by what extent. One is for first time attendees and another is for major gift prospects. 
-	At the first step, we selected the independent variables and stored the values in ‘x1, x2, x3, x4, x5’. By changing the variables in the square bracket, we tested several combinations of variables to find the best model. 
![](https://ppt.cc/fU7kWx@.png)

Then, we created a list to store 5 testing models/combinations. Before fitting the values to the regression model, we used the get_dummies() function to transform the categorical variable into a dummy variable, if any.
-	At the second step, we selected the dependent variable, which is the number of first time attendees in the data, for our first model.
-	In order to split the train and test data, at the third step, we used the train_test_split function imported from sklearn.model_selection to set the train size to 80%, and test size to 20% of the entire dataset. By using train and test data to evaluate the model, it can avoid the overfitting or underfitting issue.
-	Next, at the fourth and fifth steps, we use our train data to fit the model and predict values for getting the necessary values to generate the model performance report.
-	At step sixth and seventh, we imported mean_square_error from sklearn.metrics to get the MSE value. Moreover, we imported statsmodels.api to check the R-squared and adjusted R-square values. 
-	At the last two steps, we tested the model with train and test data to confirm the validity of the performance.
-	Using for loop function, we can quickly generate the performance of 5 models and make comparisons.
-	For the First Time Attendees Model, we decided to use Model 5, which has the highest adjusted R-square value and the lowest MSE value. Based on the regression output, we found that the number of participants, event location in the southeast area,  and events’ purpose of socializing, athletes and service have a positive influence on the number of first time attendees.  

![](https://ppt.cc/fCpXcx@.png)

➔	For the Major Prospects Model, we also decide to use Model 5, which has the highest adjusted R-square value and the lowest MSE value.Based on the regression output, we found that the average age, month, and and events’ purpose of stewardship have a positive effect on the number of major gift prospects. For the UMD alumni association, in order to increase the number of major gift prospects, having Stewardship events are highly recommended.
 
![](https://ppt.cc/fwkZkx@.png)

### 5. Summary

After an in-depth analysis of different variables that affect the number of first-time attendees and major prospects at an event, we can summarize that -

-	To increase the participation of first-time attendees, the target audience should be Students and Alumni under the age of 30. Socializing and Service events in the Southeast location and Online platforms with the activity ‘GradBash’  have also seen a great number of first-time attendees. Additionally, the event should be held from Sunday-Tuesday in the months of May, July or September to expect a greater percentage of first-time attendees. 

-	Similarly, to increase the participation of major prospects, the target audience should be Members over the age of 60. Events with Social content and the activity ‘Maryland in Manhattan’, in the Southeast and Northeast locations, have also seen a great number of major prospects. Additionally, the event should be held on a Friday, preferably in the month of September, to see the maximum percentage of major prospects. 
