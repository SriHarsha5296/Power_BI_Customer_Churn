Analysing customer churn in Power BI

We take Bank Customer Churn dataset and go through the end-to-end process of developing and publishing the Customer Churn Analysis report in Power BI, 

1.	Tools: 
•	Excel
•	Power Bi
•	DAX
•	Data Visualization

2.	Data Collection: 
             Data set Description:  it’s a European bank customer data set  
            data set added, transform data, deleting the Estimated Salary Column from the data set             because it’s not used mostly. 

a.	Removing Estimated Salary Column by selecting the whole column and remove column option in home.
b.	renaming hedder (column Names Epically changed Balance to Account Balance, Credit Card to Credit Card status, Active Member to active and Finally Churn to Churn Status) for the better Understanding and better readability.

3.	Data Preparation:

a.	Verifying the data types and editing the data types if required

b.	Added a column product similar to Product numbers which is products using add columns by Example, named products and typed prod 1 and enter and finally removing the Product type column from the table.

c.	Then went to credit card changed data type to text, replaced 1 to owned and 0 to not Owned.

d.	Renaming active to activity status, changing it to text and replacing 1 to Active and 0 to inactive.

e.	Changed churn data type from number to text and replacing 1 as churned and 0 as not churned(unchurned), Select age go to view and then select column profile.

f.	Creating a Conditional column at age, select age add column then conditional column

conditional column -> name (age GRp) -> Less than or Equal -> 20 -> <20

conditional column -> name (age GRp) -> Less than or Equal -> 30 -> 21-30

conditional column -> name (age GRp) -> Less than or Equal -> 40 -> 31- 40

conditional column -> name (age GRp) -> Less than or Equal -> 50 -> 41-50

conditional column -> name (age GRp) -> Less than or Equal -> 60 -> 51-60

conditional column -> name (age GRp) -> Less than or Equal -> 70 -> 61-70

conditional column -> name (age GRp) -> greater than or Equal -> 71-> >71

g.	Press ok, doing same for credit score, Account balance Also changing all three data types to text.

4.	Data Modelling: 

a.	Referencing for ascending and descending order, name it as age groups and then select age group, select home and them remove all columns except selected columns, then go and remove duplicated in home and in remove rows.

b.	Add conditional column
                 conditional column -> name (Age Groups id) -> Equal -> <20-> 1
                 conditional column -> name (Age Groups id) -> Equal -> <20   -> 1
                conditional column -> name (Age Groups id) -> Equal -> 21-30 -> 2
                conditional column -> name (Age Groups id) -> Equal -> 31-40 -> 3
                conditional column -> name (Age Groups id) -> Equal -> 41-50 -> 4
                conditional column -> name (Age Groups id) -> Equal -> 51-60 -> 5
               conditional column -> name (Age Groups id) -> Equal -> 61-70 -> 6
              conditional column -> name (Age Groups id) -> greater than or Equal -> >71-> 7
c.	Same doing for account balance and credit scores as well, close and apply.

5.	View And Edit Relationships:

a.	No need in this project but i you want to edit we can edit using edit relationships button.

6.	 Creating Measures using Dax:

a.	Create new measure, " Customers = Count ('Customer Data '(Customer ID)) "

b.	Create new measure, " Customers Lost = CALCULATE (COUNT ('Customer data'[Churn Status]),'Customer data'[Churn Status] = "Churned") "

c.	Create new measure, "Churned Rate = CALCULATE ('Customer data'[Customers Lost]/'Customer data'[Customers]) " and changed it to one decimal value.

7.	Data Visualization:

a.	Customers by gender visualizing by donut chat, go to format visual in visual and options as top centre, in general align the title, go to visual turn off the title.

b.	Copy and paste the same graph and then change gender by activity Status, Credit card status, country.

c.	Taking line and cluster column chat for X-axis -> Age Group, Y axis -> Customers, secondary/ line Y axis -> Churn Rate

d.	For sorting correctly, select age groups and then go to column tools, sort by, Column ID then go to graph, More options, Age Groups, sort in ascending order


e.	Taking line and cluster column chat for X-axis -> Credit Score, Y axis -> Customers, secondary/ line Y axis -> Churn Rate

f.	For sorting correctly, Select Credit Score and then go to column tools, sort by, Column ID then go to graph, More options, Credit Score, sort in ascending order

g.	Taking line and cluster column chat for X-axis -> Account Balance, Y axis -> Customers, secondary/ line Y axis -> Churn Rate

h.	For sorting correctly, Select Account Balance and then go to column tools, sort by, Column ID then go to graph, More options, Credit Score, sort in ascending order.

i.	Adding a slicer, field churn status, going to slicer settings then options, style to dropdown 

j.	Adding a Gauge, taking churn rate, we need min, max and targeted churn rate so go to transform data -> customer data -> add column -> custom column -> need 3 columns which are 

k.	Min Churn Rate, 0, customer id and change the column to %, max Churn Rate, 1, customer id and change the column to %, Target Churn Rate, 0.15, customer id and change the column to % 


8.	Preparing Dashboards:

a.	creating and adjusting all maps and Graphs, inserting rectangle boxes and Selecting Perfect template

b.	Adding background and colour grading the template as well as adding text boxes and adding Picture and finally adjusting the graphs axis and then done.
