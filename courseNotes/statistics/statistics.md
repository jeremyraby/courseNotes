# Statistics

[Freecodecamp Statistics Course](https://www.youtube.com/watch?v=xxpc-HPKN28&t=2024s)

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
  - also called "continuous"
  - can be *interval* or *ratio*
    - interval
      - no true zero
        - time of admit (to a hospital) *can't* be 0
    - ratio
      - has a true zero
        - you can have a systolic BP of 0 (you'd be dead, but it's possible)
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

## Sampling

- A sample is used to draw inferences about the population.
  - Samples are generally more practical to test than entire populations
  - to count quantitative sample sizes in Excel, use `=COUNT()` `=COUNTA()` for qualititative samples

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
