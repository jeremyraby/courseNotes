# OSEMN

[Origin](https://web.archive.org/web/20160220042455/dataists.com/2010/09/a-taxonomy-of-data-science/)

Obtain data
Scrub data
Explore data
Model data
Interpret data

## Obtain data

Answer the following questions:
- What data do I need to answer my research question?
- Where can I get these data?
  - First party
    - internal to your organization
    - most reliable
  - Second party
    - Someone else's first party data
    - You buy their data (example)
  - Third party
    - Person C buys data that Person B bought that was collected by Person A

### Evalutate data sources

Answer the following questions:
- How recent are the data?
- How were the data collected?
- Are the data sampled? How?
- How detailed are the data?
- Are there any data quality issues?
- Should/can the data be supplemented from another source/data set?

## Scrub the data

Dirty data are hard to analyze and will probably lead to inaccurate analyses
Data may be formatted differently when combining data sets
Data may contain duplicates for a number of reasons
- combining data sets
- human entry error
- machine entry error
- copy pasting error

### How to clean data

1. Remove duplicates
2. Ensure a consistent format
  - capitalization/spelling
  - dates as MM-DD-YY
  - currency
  - location (NYC, New York, Queens)
3. [Missing values](https://www.reddit.com/r/dataanalysis/comments/13ltvu1/data_cleaning_help_dealing_with_missing_entries/)
  - Fill them in
    - Can you determine the values another way (look up ages for celebrities or another data set for public salaries)?
    - "unkown", "na"
    - use mean or median (based on distribution) of the column
  - Remove the records with blanks
  - Last resort
  - Be judicious and consistent
  - **Document** the process and reasoning
4. Check for obviously incorrect data
- Negatives where that's illogical (ages)
- Unnecessary fields (not analyzing phone numbers, so they're unnecessary in your working data)
- Extra large numerical values that must have been a system error (really large purchases that are later shown as returned) and could skew results

#### How to use Excel to clean data

The basic steps for cleaning data are as follows:

> Check [here](https://support.microsoft.com/en-us/office/top-ten-ways-to-clean-your-data-2844b620-677c-47a7-ac3e-c2e157d1db19) for specific tips, functions, and features to complete the below steps directly from Microsoft Support

1. Import the data from an external data source.
2. Create a backup copy of the original data in a separate workbook.
3. Ensure that the data is in a tabular format of rows and columns with: similar data in each column, all columns and rows visible, and no blank rows within the range. For best results, use an Excel table.
4. Do tasks that don't require column manipulation first, such as spell-checking or using the Find and Replace dialog box.
5. Next, do tasks that do require column manipulation. The general steps for manipulating a column are:
- Insert a new column (B) next to the original column (A) that needs cleaning.
- Add a formula that will transform the data at the top of the new column (B).
- Fill down the formula in the new column (B). In an Excel table, a calculated column is automatically created with values filled down.
- Select the new column (B), copy it, and then paste as values into the new column (B).
- Remove the original column (A), which converts the new column from B to A.
6. Consider creating a macro if you regularly clean the same data

## Explore your data

3 steps to EDA
1. Examine distributions
- min,max,central tendency of numeric data
- top 5 values for categorical data
  - and percent of the whole
- visualize data as descriptive stats can be very deceiving otherwise
  - [Anscombe's Quartet](https://builtin.com/data-science/anscombes-quartet)
2. Examine correlations
- [Pearson correlation](https://www.scribbr.com/statistics/pearson-correlation-coefficient/#:~:text=The%20Pearson%20correlation%20coefficient%20(r,the%20relationship%20between%20two%20variables.&text=When%20one%20variable%20changes%2C%20the,changes%20in%20the%20same%20direction)
- [Scatterplots](https://www.westga.edu/academics/research/vrc/assets/docs/scatterplots_and_correlation_notes.pdf)
- [Correlation heatmaps](https://www.quanthub.com/how-to-read-a-correlation-heatmap/#:~:text=What%20is%20a%20correlation%20heatmap,closely%20related%20different%20variables%20are.)
3. Perform stat tests
- Too many possibilities to list here and they're determined by analytical objectives

## Model the data

Used to either predict or interpret data
Can also Mythbusters the model
- Can't achieve the stated business goal explicitly? Find a way that would still meet the goal and include in the report/presentation
  - Want to use Top Ten Products in a subscription to get 500 subscribers in the first year but can only get to 500+ subscribers with Top Twelve Products

> All models are wrong, but some are useful - George Box

Classification
- is this A or B?
Regression
- How much or how many?
Clustering
- What natural segments exist in the data?

## Interpret your data

Translate finding to business context
Understand results of model and then explain finding and provide actionable insights

Answer the following questions:
- What was the analytical objective?
  - helpful to always keep this in mind
- How do the data answer this question?
- What have you learned from the data?
  - How can this be applied to the business context?
- What are the most compelling ways to present the data?
- What is the overall story I want to tell?
