# Statistics

Use the following sources/courses:

[Freecodecamp Statistics Course](https://www.youtube.com/watch?v=xxpc-HPKN28&t=2024s)<br>
[Introduction to Statistics Using Google Sheets](http://www.comfsm.fm/~dleeling/statistics/text6.html)<br>
[Learn Statistics (with Google Sheets) on Udacity](https://learn.udacity.com/courses/st095)<br>
[Statistics Crash Course](https://www.youtube.com/watch?v=zouPoc49xbk&list=PL8dPuuaLjXtNM_Y-bUAhblSAdWRnmBUcr)<br>
[Statistics by Jim](statisticsbyjim.com)

## What is Statistics?

*Statistics* refers to a range of techniques to analyze, interpret, display, and base decisions upon information.

> To be an intelligent consumer of statistics, your first reflex must be to question the statistics that you encounter ... [and your second should be] to recognize statistical evidence that supports a stated conclusion.

An *individual* is a person or object included in a study.

- Can be people, records, reports, or even a geographic area

A *variable* is a characteristic of the individuals that is being studied/observed

A *population* is a group of individuals within a certain theme

- Theme = all nurses at New Amsterdam
- Population = a list of those nurses' names
- When studying a population, you take observations of each individual within the population. That study is a *census*.

A *sample* is a small subset of a larger group, or population.

A *statistic* and a *parameter* are related concepts.

- Both are descriptions of groups
  - a *parameter* is a description/measure of the whole population
    - written as Greek (eg theta) or capital letters (eg `N`)
    - mean age of every American on Medicare
  - a *statistic* is a description of a sample of the population
    - written as Roman or lowercase letters (eg `n`)
    - mean age of American on Medicare using a sample from the Medicare Beneficiary Survey
  - All the pieces in a chess set vs only the rooks

### Descriptive vs Inferential Statistics

*Descriptive statistics* are the numbers, calculations, and figures used to summarize or describe population **or** sample information (data).
  
- Descriptive statistics **do not** generalize to larger trends about a population.

Samples are used to infer, or imply, conclusions about samples in *inferential* statistics.

- Inferential stats are used to generalize to larger trends about a population.

### Classifying levels of measurement

[A 4 level system](https://github.com/jeremyraby/courseNotes/blob/main/courseNotes/statistics/classifyStatistics.jpg)

[Another model for classifying statistics](https://github.com/jeremyraby/courseNotes/blob/main/courseNotes/statistics/classifyStatistics2.jpg)

#### Quantitative vs Qualitative Data

- Quantitative
  - use of numbers to measure something
  - can be *interval* or *ratio*
    - interval
      - no true zero
        - time of admit (to a hospital) *can't* be 0
      - Median
      - Min or Max values
      - Range
    - ratio
      - has a true zero
        - you can have a systolic BP of 0 (you'd be dead, but it's possible)
      - Mean
      - Standard deviation
- Qualitative
  - use of descriptions or characteristics
  - also called "categorical"
  - can be nominal or ordinal
    - *ordinal* data have an implicit, natural order
      - can be ordered from smallest to largest
      - Sprain cetegories (1, 2, 3)
      - Best, better, good, neutral, bad, terrible, god-awful
    - *nominal* data do not have any implicit order
      - can't be ordered from smallest to largest
      - names, colors, locations

Data can also be considered either *discrete* or *continuous*. Discrete data can be either qualitative or quantitative and is specifically countable (interval) whereas contious data is always quantitative and measurable instead of countable (ratio).

## Sampling

- A sample is used to draw inferences about the population.
  - Samples are generally more practical to test than entire populations
  - to count quantitative sample sizes in Excel, use `=COUNT()` or `=COUNTA()` for qualititative samples
  - Data from a sample can be just as good as if you had surveyed the population, so long as the sample is *representative*
    - If you're studying students at a school and only include males ages 18-20, you're leaving out all the females as well as anyone older than 20. Instead, you'd want your sample to have the same percentage of males and females as are in the population, as well as the same percentages of ages/employment statuses/full or part time students, etc.

### Definitions

*Sampling Frame* is the list of individuals actually selected for the sample and could be phyical or theoretical
*Undercoverage* is when individuals who probably should be in the sample frame aren't for various reasons.
  
- If you're studying ER admissions, be sure to include admissions during the day and night

*Simulation* is a "numerical facsimilie or representation of a real-world phenomenon

### Types of Samples

- Simple Random Sampling
  - Every member of the population has an equal opportunity of being in the sample
  - 2 methods
    - Method 1
      1. Assign each individual a unique number (student ID?)
      2. Put each number in a hat or bingo thing and mix them up
      3. Draw your sample
    - Method 2
      1. Generate your own numerical list that's as long as the list of your population
        1a. make and number 10 slips of paper
      1 b. mix up the papers
      2. Randomly assign your numbers to the population list
        2a. first student in line gets the first paper pulled from the hat or bingo thing, etc
      3. Take the first `n` of your population (however many you need for your sample)
        3a. arrange them in order
        3b. take your `n`
    - Method 1 is old-fashioned and probably uses a hat, method 2 is new-school and could use Excel or another software
  - Limitations
    - You need an actual list of the population
      - Risks undercoverage
- Stratified Sampling
  - More inclusive than simple random sampling (SRS)
  - Sampling frame is divided into at least 2 groups (strata), then use simple random sampling on each stratum
    - If studying a student population, strata could be freshmen, sophomores, etc
    - More helpful than SRS if, for instance, you have a smaller number of freshmen than the other classifications. Using SRS you could, by luck, not include freshmen in your sample
  - Limitations
    - Could lead to oversampling a stratum and biasing your sample
    - Must have an actual list, as with SRS
    - Gotta figure out how to build your strata
      - must know if a hospital is urban or rural

> For both Simple Random Sampling and Stratified Sampling, Excel can be used to generate pseudo-random numbers.

> `=RAND()` will generate a random decimal number between 0 and 0.999...

> Converting `=RAND()` to an interval can be done with the `=INT()` function: `=INT(RAND())`

> To simulate flipping a coin, with 1 being heads and 0 tails, use `=INT(RAND()*2)` {"heads" or "tails" can be added like this `=CHOOSE(INT(RAND()*2),"head","tail")`}

## Types of Studies

Observational studies and surveys can only show relationships. Only controlled experiments can show causation.

In experiments, we study & manipulate **independent variables**, measure changes in **dependent variables** and try to control **lurking variables** that could affect the dependent variables.


## Central Tendency

3 measurements
- Mean (average)
  - (sum of dataset) / (count of all records in the dataset)
  - `=AVERAGE()`
  - Exaggerated by abnormally small or large values
  - *Use to describe how much money each customer spent at a store over a period of time*
- Median (middle)
  - Half the records are smaller than the median and half are larger
  - Order the records from smallest to highest
    - Find the record in the middle
    - For even numbered datasets, avergage the 2 numbers in the middle
  - `=MEDIAN()`
  - When outliers are present, median is more accurate of the dataset's center
  - *Use to how much money the typical customer spent at a store during a period of time*
- Mode (most common)
  - Nice to know, but not useful for making decisions
  - Order the records from smallest to highest
    - Find the most common record
  - `=MOD.SNGL()` for a range
  - `=MOD.MULT()` for an array
    - "bimodal" because there are 2 modes for the dataset
  - *Use to describe which was the most popular product at a store during a period of time*

## Variability

How close or spread away the data points are to/from the center
- Low variability = clustered around the center
  - "consistent"
- High variablility = spread out away from the center
  - "inconsistent"
  - extreme values become more likely
    - "out of spec"
- [Helps us grasp the likelihood of unusual events](https://statisticsbyjim.com/basics/variability-range-interquartile-variance-standard-deviation/)

- Range
  - (largest data point) - (smallest data point)
  - Most useful for 
    - describing data *without* extreme values
      - Outliers will exaggerate the range and cause it to be misleading
    - smaller data sets
      - Larger data sets will probably have a larger range
        - Differing sample sizes aren't comparable

- Interquartile Range (IQR)
  - Middle *half* of the data
  - Not influenced by outliers
    - used for skewed distributions
      - As with medians
  - To find:
    1. List data in numeric order
    2. Find the 3 values that "cut" the data into quarters
        - If the value is a decimal, average 2 adjacent values
        - Q2 = median
    3. IQR = (Q3 - Q1)

- Variance
  - Average squared difference between each data point and the mean
  - Multistep formula
    - Use software to run these calculations
    - "N" & "N-1" are commonly used in the formula if calculating for population or sample, respectively
      - "N" = the population size
      - "N-1" = the sample size
        - accounts for the sample to underestimate population variance
    1. Calculate the mean for the dataset
    2. Subtract the mean from each datapoint and keep the absolute value
    3. Square each difference ie (|datapoint - mean|)^2
    4. Calculate the mean of the now squared values
        - N-1 for samples

- Standard deviation
  - Typical difference between each data point and the mean
  - Reported in the same units as the dataset, making interpretation convenient
    - Easier to interpret than variance because it's not reported as a squared value
  - Multistep formula
    - Use software to run these calculations
    - Square root of the variance
    1. Calculate the mean for the dataset
    2. Subtract the mean from each datapoint and keep the absolute value
    3. Square each difference ie (|datapoint - mean|)^2
    4. Calculate the mean of the now squared values
        - N-1 for samples
    5. Calculate the square root of the new mean
        - What value, squared, equals the mean?
  - `=STDEV.S()` for samples
  - `=STDEV.P()` for populations
  - z-score
    - Used to describe individual datapoints within a dataset and their relationship to the mean
    - A datapoint's distance from the mean in standard deviations
    - (datapoint - mean) / standard deviation
      - positive or negative
        - larger/higher/above than the mean
        - smaller/lower/below than the mean
      - smaller z-scores are more similar to the mean than larger z-scores

**Which measure of central tendency and variability should I use?**

- If it's a small dataset with no outliers, use mean and range
- If the data are normally distributed, use mean and standard deviation
- If the data are skewed, use median and IQR or another percentile measurement

### The Empirical Rule

For normally distributed datasets (bell curve), most datapoints will fall within 3 standard deviations of the mean
- 68% within 1 sd
- 95% within 2 sd
- 99.7% within 3 sd

#### Outliers

- Surprisingly no hard and fast definition of an outlier
  - Could be any datapoint more than 2 sd from the mean or just an unexpected value (big stock drops in a single day)
  - Can be identified with IQR
    - lower "fence" = (Q1 - (1.5 * IQR))
    - upper "fence" = (Q3 + (1.5 * IQR))
    - Anything below/above these "fences" is a potential outlier

- Will affect the mean
  - Left (extra small value) or right (extra large value) skewed when graphed as a histogram
    - Makes the median the more useful stat in this instance

- Typically 3 causes
  - Data entry
    - Dirty data
      - Can be cleaned
        - Corrected
        - Imputed with the mean or median?
    - If part of a study you're doing, try to redo the measurement to get accurate data
  - Sample problems/unusual conditions
    - Individual doesn't actually meet inclusion criteria
  - Natural variation
    - Not a problem
      - Law of large numbers says some extremes will occur
      - Study it! It could be instructive.
      - In a normal distribution 1 / 340 observations (0.0029%) will be at least 3 sd away from the mean
      - Although rare, even small datasets can have extreme values

> Remove the datapoint if it either can't be corrected or doesn't meet inclusion criteria

> Do not remove a datapoint to produce a more desirable result (better fitting model or statistical significance)

- [When encountering outliers, ask 4 questions](https://statisticsbyjim.com/basics/remove-outliers/):
  - Is it really an outlier?
  - How'd it happen?
    - Power outage during a production process?
    - Diabetic patient in a study of a "healthy" population?
    - Dirty data?
  - What can we learn from it?
    - Run analyses both with and without the outlier and make comparisons
      - Possibly include in final reporting
  - Should we change something to take advantage of what we've learned from the outlier?

> Document the shit out of your process and reasoning for removing or imputing datapoints

## Percent Comparisons

### Percent Change

- Use when comparing an *old* value to a *new* value
- (((new - old) / |old|) * 100)
- Positive value = increase
- Negative value = decrease

### Percent Error

- Use when comparing an *approximate* value to an *exact* value
- (((|approx - exact|) / |exact|) * 100)
- Report absolute value unless you want to know over/under the exact value

### Percent Difference

- Use when both values are equally important; one is not obviously older or better
- (|(first value - second value) / ((first + second) / 2)| * 100)
- Report absolute value

### Percentage Points

**Not the same as %change, %error, or %difference**

Literally the diffrence between percentage values

Avoid reporting confusion
- An increase/decrease in B percentage points != an increase/decrease of B%
  - A change of 2 percentage points from 10% to 12% is an increase of 20% (12 / 10 = 1.2 = 120% = increase of 20%)
    - % is a ratio of two values, in this case a percentage change
- When in doubt, report both: "Interest rates increased by 2 percentage points today, meaning a 20% increase in interest payments"

### Per capita (rate) Comparisons

- Allows an apples to apples comparison between samples/populations
  - better than comparing raw numbers
- Technically, per capita = each individual, but other rates may be used eg "per 100k"
- Take your statistic number and divide by `n` then multiply by 100k
  - 50 murders in City A of 800,000 people
    -  ((50 / 800,000) * 100,000) = 6.25 murders *per 100k people*
  - 50 murders in City B of 600,000 people
    - ((50 / 600,000) * 100,000) = 8.33 murders *per 100k people*
  - City B has a higher muder rate

## Probablility

Study of chance and how likely an event is to occur
