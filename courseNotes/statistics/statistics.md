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

A 4 level system

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

![How to classify statistics algorithm](~/Documents/development/courseNotes/statistics/classifyStatistics.jpg)

## Sampling

- A sample is used to draw inferences about the population.
  - Samples are generally more practical to test than entire populations
  - Samples must be *representative* of the larger population
    - When samples are *random* we can assume they're representative as long as the sample is large enough
    - Random sampling ensures that every member of the study population has an *equal chance* at being selected for the sample

> When studying voter preferences, a sample of only men or only senior citizens isn't representative of the whole population. Those samples would be *biased*.

- Sample size is also important as a random, but small, sample could still be biased.
- Simple random sampling isn't always the best option, s0 other means of ensuring representative samples have been developed.
  - *Random assignment* is when a sample is split into different study groups eg treatment & control groups
  - *Stratified sampling* is when a population consists of 2 or more natural sub-groups and the test sample is made to reflect those groups.
    > Suppose you were interested in views of capital punishment at an urban university. You have the time and resources to interview 200 students. The student body is diverse with respect to age; many older people work during the day and enroll in night courses (average age is 39), while younger students generally enroll in day classes (average age of 19). It is possible that night students have different views about capital punishment than day students. If 70% of the students were day students, it makes sense to ensure that 70% of the sample consisted of day students. Thus, your sample of 200 students would consist of 140 day students and 60 night students. The proportion of day students in the sample and in the population (the entire university) would be the same. Inferences to the entire population of students at the university would therefore be more secure.