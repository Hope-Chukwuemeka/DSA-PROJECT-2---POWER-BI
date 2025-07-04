### DSA-PROJECT-2---POWER-BI
This project is based on salvaging the Palmora Group from gender-related issues tailored to - gender distribution, ratings based on gender, gender pay gap on salaries and lots more...

CASE STUDY 3: Palmora Group HR Analysis   -     POWER BI

#### STEPS IN POWER BI TABLE

2 files were shared for this purpose
First is to confirm the dataset to be sure all what are stated in the requirements are truly what they are.
However, before I upload the dataset into Power BI, I needed to fix the *Gender Column* on excel first, as to apportion gender to those staff who decided not to disclose their gender.
So there was need for me to determine the no of blanks to fill for genders.
Then apply to execute *=COUNTBLANK(B:B)* in a cell outside the data set. Since the pressing issue is about gender equality. So I applied the formula on cell *H2* to easily know how many of them. 
 - In data analysis, you can either use N/A meaning not available for characters or 0 for numbers. Where we are unsure.
Apply Filter to the dataset to filter out *Blanks* on the Gender Column. Once the Blanks are Filtered out, Type N/A on the 1st blank cell. Then use auto fill to fill all the blanks
With that we just fulfilled this 1st requirement.Save your file and close it. Its ready for Power BI transformation.

#### Going ahead to launch Power BI

On the Home page, click *Get Data* because your emp-data is in csv format. So choose your csv option
Then go ahead and click *Transform Data* as appropriate

Lets fulfill this requirement - Some employees are without a salary because they are no longer with the company. All of those employees were taken out.
In actual fact, its really difficult to delete in-between rows - Using *Salary* filter and unselect ONLY *(null)*. Then click *OK*. Checking the *Column Quality*, it will return 100%. So the same is done for *Department*
Rename the *Location* header as *Region*. Once it is done than, click *Keep Rows* >>>> *Keep Top Rows*. Then input the *946*
Click *Close & Apply*. This is done so that the Nulls wont return with the data again. Pick up the Dataset again and relaunch it for transformation. Reconfirm that the nulls are no longer there... 

#### The Bonus Rules File:
Please note that the file format is Excel. So click *Close & Apply* again for the emp_data For us to transform the Bonus Rules.
Hold your *Ctrl* down to select *All The Columns* EXCEPT Department. While you still have those columns selected, click on *Unpivot Columns*
NEXT, we need to create a unique relationship between the 2 tables that is beyond Department... this is done By creating a *Custom Column*
You can call it *Dept_Rating*
This is what we have to concatenate - *[Department]&"/"&[Attribute]*. click ok. Then close and apply.
Doing the same for - Palmora Group Emp_Data
This is what you have there *[Department]&"/"&[Rating]* Then click Ok
Create *Custom Column* for Palmoria Group Emp_Data. So now that you also have same with the emp_data, we will proceed to Merge the 2 datasets.
Using *Merge Queries as New*

- *Dept_Rating* is the relationship that exist between the 2 datasets. Then click Ok

Select only the *Value* once you click the filter on the Bonus mapping column. After that, then OK. Once you do that, the column name is changed to *Bonus Rate*
However, The Column Quality is not 100% because of some cells. These are actually those staff that are not rated. Which means they are not entitled to bonus. They are the ones representing *Null* here. 

*Replace Values* is done here by doing a right click to replace them with *0*, then Click OK. Once this is done, Column Quality bacame 100%.
NEXT is to formulate *Annual Bonus* base on the assigned Bonus Rate per Staff
Which is represented by = [Salary]*[Bonus Rate]

For each staff Total Salary inclusive Bonus, another custom column. 
Then to get Total Pay = [Salary]+[Annual Bonus]
To close this session, lets fulfill this requirement too - Show the pay distribution of employees grouped by a band of $10,000. For example: and How many employees fall into a band of $10,000 – $20,000, $20,000 – $30,000, etc
To fulfill that, you apply your *Conditional Column*
So to monitor if the coy meets industry regulation minimum of *90,000*, I decided to keep it the highest as *Above 120,000*
Then Close & Apply
Finally the “Merged” was renamed because this Dataset is where the visuals will be done.
After that, click Home to Save your Project

### Tools Used:
- Microsoft Power BI   [Download here](https://www.microsoft.com/en-us/download/details.aspx?id=58494&msockid=0bb0c76f3ee562ab2697d3583ff7637f)
- Data Transformation
- Report Presentation
- For visualization
- Data Modelling

#### THe visualization is done and also attached here.
