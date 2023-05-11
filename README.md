# Exploratory-Data-Analysis--Retail-
content://media/external/downloads/72279




Exploratory Data Analysis-Retail#Task3 Last Checkpoint: 4 minutes ago (autosaved)  Logout
Menu
Python 3 (ipykernel)

Trusted
File
New NotebookDropdown
Python 3 (ipykernel)
Open...
Make a Copy...
Save as...
Rename...
Save and CheckpointCtrl-S
Revert to CheckpointDropdown
Wednesday, May 10, 2023 5:37 PM
Print Preview
Download asDropdown
AsciiDoc (.asciidoc)
HTML (.html)
LaTeX (.tex)
Markdown (.md)
Notebook (.ipynb)
PDF via LaTeX (.pdf)
reST (.rst)
Python (.py)
Reveal.js slides (.slides.html)
PDF via HTML (.html)
Deploy as
Trusted Notebook
Close and Halt
Edit
Cut CellsX
Copy CellsC
Paste Cells AboveShift-V
Paste Cells BelowV
Paste Cells & Replace
Delete CellsD,D
Undo Delete CellsZ
Split CellCtrl-Shift-Minus
Merge Cell Above
Merge Cell Below
Move Cell Up
Move Cell Down
Edit Notebook Metadata
Find and Replace
Cut Cell Attachments
Copy Cell Attachments
Paste Cell Attachments
Insert Image
View
Toggle Header
Toggle Toolbar
Toggle Line NumbersShift-L
Cell Toolbar
None
Edit Metadata
Raw Cell Format
Slideshow
Attachments
Tags
Insert
Insert Cell AboveA
Insert Cell BelowB
Cell
Run CellsCtrl-Enter
Run Cells and Select BelowShift-Enter
Run Cells and Insert BelowAlt-Enter
Run All
Run All Above
Run All Below
Cell Type
CodeY
MarkdownM
Raw NBConvertR
Current Outputs
ToggleO
Toggle ScrollingShift-O
Clear
All Output
Toggle
Toggle Scrolling
Clear
Kernel
InterruptI,I
Restart0,0
Restart & Clear Output
Restart & Run All
Reconnect
Shutdown
Change kernel
Python 3 (ipykernel)
Widgets
Save Notebook Widget State
Clear Notebook Widget State
Download Widget State
Embed Widgets
Help
User Interface Tour
Keyboard ShortcutsH
Edit Keyboard Shortcuts
Notebook Help
Markdown
Python Reference
IPython Reference
NumPy Reference
SciPy Reference
Matplotlib Reference
SymPy Reference
pandas Reference
About




Run



xxxxxxxxxx
# ORGANIZATION:THE SPARKS FOUNDATION
​
BY:MONJOK JOSEPH TEREM
​
DOMAIN:DATA SCIENCE & BUSINESS ANALYTICS
​
TYPE:INTERNSHIP(GRADUATE ROTATIONAL INTERNSHIP PROGRAM)
​
​
TASK:3
ORGANIZATION:THE SPARKS FOUNDATION¶
BY:MONJOK JOSEPH TEREM

DOMAIN:DATA SCIENCE & BUSINESS ANALYTICS

TYPE:INTERNSHIP(GRADUATE ROTATIONAL INTERNSHIP PROGRAM)

TASK:3


xxxxxxxxxx
 
# PROBLEM STATEMENT
As a Business manager,try to find out the weak areas where you can work on to make more profits
PROBLEM STATEMENT¶
As a Business manager,try to find out the weak areas where you can work on to make more profits


xxxxxxxxxx
 
# 1).DATA DESCRIPTION
Task-03(Exploratory Data Analysis-Retail on dataset'SampleSuperStore')
​
​
The information on the dataset are as follows:
.Shipmode
.Segment
.Country,City and State
.Region
.Cartegory
.Sales
.Quantity
.Discount
.Profit
1).DATA DESCRIPTION¶
Task-03(Exploratory Data Analysis-Retail on dataset'SampleSuperStore')

The information on the dataset are as follows: .Shipmode .Segment .Country,City and State .Region .Cartegory .Sales .Quantity .Discount .Profit

In [2]:

#Importing the required Librearies
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
%matplotlib inline
import seaborn as sns
import statsmodels.api as sm
import scipy.stats as stats
import copy
import os
import ipywidgets as widgets
​
In [16]:

os.getcwd()#This function gets the file directory from your computer
Out[16]:
'C:\\Users\\Monjok J\\Downloads\\The Sparks Foundation completed Tasks'
In [34]:

x
#Read the data
df=pd.read_excel('C:/Users/Monjok J/Downloads/The Sparks Foundation completed Tasks/Exploratory Data Analysis/SampleSuperstore.xlsx')
print(df)
​
​
           Ship Mode    Segment        Country             City       State  \
0       Second Class   Consumer  United States        Henderson    Kentucky   
1       Second Class   Consumer  United States        Henderson    Kentucky   
2       Second Class  Corporate  United States      Los Angeles  California   
3     Standard Class   Consumer  United States  Fort Lauderdale     Florida   
4     Standard Class   Consumer  United States  Fort Lauderdale     Florida   
...              ...        ...            ...              ...         ...   
9989    Second Class   Consumer  United States            Miami     Florida   
9990  Standard Class   Consumer  United States       Costa Mesa  California   
9991  Standard Class   Consumer  United States       Costa Mesa  California   
9992  Standard Class   Consumer  United States       Costa Mesa  California   
9993    Second Class   Consumer  United States      Westminster  California   

      Postal Code Region         Category Sub-Category     Sales  Quantity  \
0           42420  South        Furniture    Bookcases  261.9600         2   
1           42420  South        Furniture       Chairs  731.9400         3   
2           90036   West  Office Supplies       Labels   14.6200         2   
3           33311  South        Furniture       Tables  957.5775         5   
4           33311  South  Office Supplies      Storage   22.3680         2   
...           ...    ...              ...          ...       ...       ...   
9989        33180  South        Furniture  Furnishings   25.2480         3   
9990        92627   West        Furniture  Furnishings   91.9600         2   
9991        92627   West       Technology       Phones  258.5760         2   
9992        92627   West  Office Supplies        Paper   29.6000         4   
9993        92683   West  Office Supplies   Appliances  243.1600         2   

      Discount    Profit  
0         0.00   41.9136  
1         0.00  219.5820  
2         0.00    6.8714  
3         0.45 -383.0310  
4         0.20    2.5164  
...        ...       ...  
9989      0.20    4.1028  
9990      0.00   15.6332  
9991      0.20   19.3932  
9992      0.00   13.3200  
9993      0.00   72.9480  

[9994 rows x 13 columns]
In [37]:

xxxxxxxxxx
df.head(10)#Prints out the number of rows(0-9) from the top
​
Out[37]:
Ship Mode	Segment	Country	City	State	Postal Code	Region	Category	Sub-Category	Sales	Quantity	Discount	Profit
0	Second Class	Consumer	United States	Henderson	Kentucky	42420	South	Furniture	Bookcases	261.9600	2	0.00	41.9136
1	Second Class	Consumer	United States	Henderson	Kentucky	42420	South	Furniture	Chairs	731.9400	3	0.00	219.5820
2	Second Class	Corporate	United States	Los Angeles	California	90036	West	Office Supplies	Labels	14.6200	2	0.00	6.8714
3	Standard Class	Consumer	United States	Fort Lauderdale	Florida	33311	South	Furniture	Tables	957.5775	5	0.45	-383.0310
4	Standard Class	Consumer	United States	Fort Lauderdale	Florida	33311	South	Office Supplies	Storage	22.3680	2	0.20	2.5164
5	Standard Class	Consumer	United States	Los Angeles	California	90032	West	Furniture	Furnishings	48.8600	7	0.00	14.1694
6	Standard Class	Consumer	United States	Los Angeles	California	90032	West	Office Supplies	Art	7.2800	4	0.00	1.9656
7	Standard Class	Consumer	United States	Los Angeles	California	90032	West	Technology	Phones	907.1520	6	0.20	90.7152
8	Standard Class	Consumer	United States	Los Angeles	California	90032	West	Office Supplies	Binders	18.5040	3	0.20	5.7825
9	Standard Class	Consumer	United States	Los Angeles	California	90032	West	Office Supplies	Appliances	114.9000	5	0.00	34.4700
In [39]:

df.tail(10)#Prints out the number of rows from the bottom of the spreedsheet
Out[39]:
Ship Mode	Segment	Country	City	State	Postal Code	Region	Category	Sub-Category	Sales	Quantity	Discount	Profit
9984	Standard Class	Consumer	United States	Long Beach	New York	11561	East	Office Supplies	Labels	31.500	10	0.0	15.1200
9985	Standard Class	Consumer	United States	Long Beach	New York	11561	East	Office Supplies	Supplies	55.600	4	0.0	16.1240
9986	Standard Class	Consumer	United States	Los Angeles	California	90008	West	Technology	Accessories	36.240	1	0.0	15.2208
9987	Standard Class	Corporate	United States	Athens	Georgia	30605	South	Technology	Accessories	79.990	1	0.0	28.7964
9988	Standard Class	Corporate	United States	Athens	Georgia	30605	South	Technology	Phones	206.100	5	0.0	55.6470
9989	Second Class	Consumer	United States	Miami	Florida	33180	South	Furniture	Furnishings	25.248	3	0.2	4.1028
9990	Standard Class	Consumer	United States	Costa Mesa	California	92627	West	Furniture	Furnishings	91.960	2	0.0	15.6332
9991	Standard Class	Consumer	United States	Costa Mesa	California	92627	West	Technology	Phones	258.576	2	0.2	19.3932
9992	Standard Class	Consumer	United States	Costa Mesa	California	92627	West	Office Supplies	Paper	29.600	4	0.0	13.3200
9993	Second Class	Consumer	United States	Westminster	California	92683	West	Office Supplies	Appliances	243.160	2	0.0	72.9480

xxxxxxxxxx
 
# 2).EXPLORATORY DATA ANALYSIS(WITH PYTHON)
​
2).EXPLORATORY DATA ANALYSIS(WITH PYTHON)¶
In [40]:

 
df.info()#Gives a short description of the content in the data set
<class 'pandas.core.frame.DataFrame'>
RangeIndex: 9994 entries, 0 to 9993
Data columns (total 13 columns):
 #   Column        Non-Null Count  Dtype  
---  ------        --------------  -----  
 0   Ship Mode     9994 non-null   object 
 1   Segment       9994 non-null   object 
 2   Country       9994 non-null   object 
 3   City          9994 non-null   object 
 4   State         9994 non-null   object 
 5   Postal Code   9994 non-null   int64  
 6   Region        9994 non-null   object 
 7   Category      9994 non-null   object 
 8   Sub-Category  9994 non-null   object 
 9   Sales         9994 non-null   float64
 10  Quantity      9994 non-null   int64  
 11  Discount      9994 non-null   float64
 12  Profit        9994 non-null   float64
dtypes: float64(3), int64(2), object(8)
memory usage: 1015.1+ KB
In [41]:

 
#Checking the missing Values in any column
df.isnull().sum()
Out[41]:
Ship Mode       0
Segment         0
Country         0
City            0
State           0
Postal Code     0
Region          0
Category        0
Sub-Category    0
Sales           0
Quantity        0
Discount        0
Profit          0
dtype: int64
In [42]:

df.describe()
Out[42]:
Postal Code	Sales	Quantity	Discount	Profit
count	9994.000000	9994.000000	9994.000000	9994.000000	9994.000000
mean	55190.379428	229.858001	3.789574	0.156203	28.656896
std	32063.693350	623.245101	2.225110	0.206452	234.260108
min	1040.000000	0.444000	1.000000	0.000000	-6599.978000
25%	23223.000000	17.280000	2.000000	0.000000	1.728750
50%	56430.500000	54.490000	3.000000	0.200000	8.666500
75%	90008.000000	209.940000	5.000000	0.200000	29.364000
max	99301.000000	22638.480000	14.000000	0.800000	8399.976000
In [ ]:

​
In [ ]:

 
​
In [47]:

xxxxxxxxxx
df.hist(figsize=(20,20))
Out[47]:
array([[<Axes: title={'center': 'Postal Code'}>,
        <Axes: title={'center': 'Sales'}>],
       [<Axes: title={'center': 'Quantity'}>,
        <Axes: title={'center': 'Discount'}>],
       [<Axes: title={'center': 'Profit'}>, <Axes: >]], dtype=object)

In [60]:

#Measuring the Skewness of the required columns
from scipy.stats import skew
​
Sales_skewness=skew(df['Sales'])
Profit_skewness=skew(df['Profit'])
Discount_skewness=skew(df['Discount'])
Quantity_skewness=skew(df['Quantity'])
​
print("Skewness of 'sales' column:", Sales_skewness)
print("Skewness of 'profit' column:",Profit_skewness)
print("Skewness of 'Discount' column:",Discount_skewness)
print("Skewness of 'Quantity' column:",Quantity_skewness)
​
​
Skewness of 'sales' column: 12.970805179533526
Skewness of 'profit' column: 7.560296619477546
Skewness of 'Discount' column: 1.6840419409939928
Skewness of 'Quantity' column: 1.2783528478702606

xxxxxxxxxx
 
# From the Skewness values of each column from the above chart,you will find out that: 
1).The Skewness of "Sales " is highly skewed(to the left )
2).That of Profit is balanced(it's at its center) and;
3).That of the Quantity and Discount vary
From the Skewness values of each column from the above chart,you will find out that:¶
1).The Skewness of "Sales " is highly skewed(to the left ) 2).That of Profit is balanced(it's at its center) and; 3).That of the Quantity and Discount vary

In [64]:

#OUTLIERS(Here,Box plot checks the outliers)
plt.figure(figsize=(20,20))
plt.subplot(3,1,1)
sns.boxplot(x=df.Sales,color='Blue')
​
plt.subplot(3,1,2)
sns.boxplot(x=df.Profit,color='Blue')
​
plt.subplot(3,1,3)
sns.boxplot(x=df.Discount,color='Green')
plt.show()


x
 
# PLOT COUNT(To Analyze the Data)
PLOT COUNT(To Analyze the Data)¶
In [69]:

sns.countplot(x=df.Category)
Out[69]:
<Axes: xlabel='Category', ylabel='count'>


xxxxxxxxxx
# The Purchase count in the 'consumer' segment is more than that of the corporate and that of the home office.
​
sns.countplot(x=df.Segment)
​
​
The Purchase count in the 'consumer' segment is more than that of the corporate and that of the home office.¶
sns.countplot(x=df.Segment)

In [71]:

sns.countplot(x=df.Discount)
Out[71]:
<Axes: xlabel='Discount', ylabel='count'>


xxxxxxxxxx
​
​
​
    
From the chart below,there are seventeen(17) Sub-Categories present in the data-set.Binders sold most compared to other sub categories and it can be visualized above¶
In [79]:

 
plt.figure(figsize=(20,20))
sns.countplot(x=df['Sub-Category'])
​
Out[79]:
<Axes: xlabel='Sub-Category', ylabel='count'>


xxxxxxxxxx
 
#There are seventeen(17) sub-categories in total and the one with the highest count is that of the Binders sub-category.
This shows that the resulting countplot would have a count above 1400 representing the number of times each unique value appears in the 'sub-category' colum.
#There are seventeen(17) sub-categories in total and the one with the highest count is that of the Binders sub-category. This shows that the resulting countplot would have a count above 1400 representing the number of times each unique value appears in the 'sub-category' colum.

In [94]:

 
sns.countplot(x=df.Region)
Out[94]:
<Axes: xlabel='Region', ylabel='count'>


x
# The Western region having the highest number of sales count
The Western region having the highest number of sales count¶
In [100]:

x
​
Out[100]:
<Axes: xlabel='Sales', ylabel='count'>


xxxxxxxxxx
 
# BIVIRATE DISTRIBUTION
BIVIRATE DISTRIBUTION¶
In [99]:

sns.pairplot(df)
plt.show()


xxxxxxxxxx
 
# GENERATING INSIGHTS FROM THE GIVEN COLUMNS
​
GENERATING INSIGHTS FROM THE GIVEN COLUMNS¶
In [ ]:

 
​
In [110]:

xxxxxxxxxx
 
#TOTAL SALES
import pandas as pd
​
df=pd.read_excel('C:/Users/Monjok J/Downloads/The Sparks Foundation completed Tasks/Exploratory Data Analysis/SampleSuperstore.xlsx')
​
total_sales=df['Sales'].sum()
print('Total sales:$',total_sales)
​
total_profit=df['Profit'].sum()
print('Total_profit:$',total_profit)
​
profit_margin=total_profit/total_sales
print(profit_margin)
Total sales:$ 2297200.8603000003
Total_profit:$ 286397.0217
0.12467217240315603
In [129]:

#Group the data by ship mode and calculate the average profit for each mode
​
print(df.columns)
profit_by_shipmode=df.groupby('Ship Mode')['Profit'].mean()
print('Profit from ship mode:$',profit_by_shipmode)
Index(['Ship Mode', 'Segment', 'Country', 'City', 'State', 'Postal Code',
       'Region', 'Category', 'Sub-Category', 'Sales', 'Quantity', 'Discount',
       'Profit'],
      dtype='object')
Profit from ship mode:$ Ship Mode
First Class       31.839948
Same Day          29.266591
Second Class      29.535545
Standard Class    27.494770
Name: Profit, dtype: float64
In [125]:

#Group the data by category and calculate the total_sales and profit for each cartegory
sales_by_category=df.groupby('Category')['Profit'].sum()
profit_by_category=df.groupby('Category')['Profit'].sum()
​
print("Sales by category:$",sales_by_category)
​
print("Profit by category:$",profit_by_category)
Sales by category:$ Category
Furniture           18451.2728
Office Supplies    122490.8008
Technology         145454.9481
Name: Profit, dtype: float64
Profit by category:$ Category
Furniture           18451.2728
Office Supplies    122490.8008
Technology         145454.9481
Name: Profit, dtype: float64
In [130]:

xxxxxxxxxx
#Another way in plotting Histograms
plt.hist(df['Discount'],bins=10)
plt.xlabel('Discount')
plt.ylabel('Count')
plt.title('DISTRIBUTION OF DISCOUNTS')
plt.show()
​


xxxxxxxxxx
 
# IN CONCLUSION
​
IN CONCLUSION¶

xxxxxxxxxx
 
#Based on the information Provided,here are some potential insights drawn from the data:
    1).The Western region in the United state is an important market for the retail company. The company may need to focus on expanding its operations in this region and also increase market efforts to capitalize on this market.
    
    2).The retail company may need to investigate its pricing strategy and consider offering more targeted or enticing discounts.
    
    3).Office Supplies are in high demand and may be a profitable product category for the company
    
    4).The Furniture and Technological utilities are also popular categories and the company may want to ensure strong 
    product offering in these categories and invest in marketing efforts to increase sales.
    
    
    it is important to keep in mind that these insights are based on the information provided. Further analysis and exploration may be necessary to fully understand the trends and patterns in the data.Hence,additional context may be required if not necessarily accurate.
#Based on the information Provided,here are some potential insights drawn from the data: 1).The Western region in the United state is an important market for the retail company. The company may need to focus on expanding its operations in this region and also increase market efforts to capitalize on this market.

2).The retail company may need to investigate its pricing strategy and consider offering more targeted or enticing discounts.

3).Office Supplies are in high demand and may be a profitable product category for the company

4).The Furniture and Technological utilities are also popular categories and the company may want to ensure strong 
product offering in these categories and invest in marketing efforts to increase sales.


it is important to keep in mind that these insights are based on the information provided. Further analysis and exploration may be necessary to fully understand the trends and patterns in the data.Hence,additional context may be required if not necessarily accurate.
In [ ]:

 
​
