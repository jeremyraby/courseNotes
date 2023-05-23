# Problem solving

> Problems != objectives
Problem: I have a dataset of all the soccer matches played in the English Premier League during the 2018-2019 season. I want to know which club is the best.
Objectives need to be specific and measurable ways of solving the problem.
Objective: Which club won the most matches? Which club had the most league points at the end of the season? Are they the same club? Which club had the fewest fouls? Which club maintained posession the longest?

## 4 Pillars of Computational Thinking

1. Problem decomposition
- Eat the elephant one bite at a time
2. Pattern recognition
- Make connections with previous experience
3. Abstraction / generalization
- Only consider important info
4. Algorithms
- Recipes / cookbooks

## George Polya's Problem Solving Method

1. Understand the problem
  - Figure out what is known, unknown, etc.
  - Is the problem similar to other problems you've seen/solved before?
2. Make a plan to solve the problem
  - Break it into smaller, simpler problems
  - Elimnate possibilities
  - Make a list
  - Draw a picture / mind map
3. Execute the plan
  - if the plan isn't working, go back to step 2 and choose a different plan
4. Check the results and revise if possible/necessary

# Descriptive Analysis - What's happening?

## Data Preparation

Data aren't always in a useable format.
- Duplicates
- Incorrect data
- Poor formatting
- Missing data

## Proxy Measures

If there's no direct way to measure something (laziness of a class), proxy measures (class average) may be used.

Proxy measures are never perfect and require you to use one or more indicators to interpret what you want to know.
- Multiple factors could bring down a class average that have nothing to do with "laziness."
  - Can cause a positive feedback loop that may cause the proxy measure to look worse over time
  - Ensure that whatever proxy is used isn't biased favoring/against what you're measuring
- Force you to fill knowlegde gaps with biases and assumptions
  - May even make you feel like you'll never have enough data to make a decision

# Diagnostic analysis - Why is it happening?

Diagnose the **cause** of a problem

Use logic

If the premises are true, the conclusion must be true.

All premises have some assumption(s) we take for granted; if the assumptions are weak so too will be the premises.

*Noise* are data points that are irrelevant to the question/situation

To refute a justification, attack the premises - once the premises are in doubt the conclusion will be doubted.

The more justifications we can gather from the data that lead to the same conclusion, the more confident we can be in the conclusion
  - corroborating evidence

## Justification Strategies

- Negative Justification
  - X **is not** the murder weapon
  - Proving why X isn't the case.
    - Easier to do; you only need 1 piece of evidence to disprove something being the case
    - Can use other relevant data to support the case
  - Can only confirm what **is not** the case
    - X **is not** the murder weapon because Y
    - Eliminate possibilities
- Positive Justifcation
  - X **is** the murder weapon
  - Used to prove the conclusion *after* negative justification eliminates other possibilities
    - Need more than 1 piece of evidence
      - Corroborating evidence
      - Confirmation bias is possible here
    - Use negative justification to determine if false

# Modeling

A good model provides a good **estimate** of what you're trying to do.

Computational problem solving is a two step process during which data will be translated and to some extent distorted:

Stuff in the real world --> Translation --> Model --> Algorithim
                         ^                         ^
                         |                         |
                     Distortion                Distortion

Real world problem --> Pattern recognition + Abstraction --> Problem as an abstract model

Pattern recognition involves observing multiple samples and noting which characterstics seem common among them.
Abstraction involves determining which characteristics are necessary, contingent, and sufficient, then ignoring the contingent characterstics and focusing on those that are both necessary *and* sufficient.
- necessary = **always** true in **all** cases
- contingent = not necessary, but may be true in some cases; still fits the pattern
- sufficient = meets definitional conditions
*A sandwich is generally sliced meat placed between sliced bread and may have other ingredients such as cheese or vegetables, but sliced meat between pita bread isn't sufficently a sandwich because the bread is different.*

Models are based on observations and exclude things we haven't observed or considered
- It's extremely hard to consider *all* possible factors - models are never 100%
  - If we're too imprecise we include irrelevant factors in the model, but if we're too precise we can still exclude relevant factors
- Tend to set expectations for what is considered "normal"
  - Ugly carrots
  - may alter behavior
    - uncritical use of models can create a positive feedback loop where the model informs reality which then starts to resemble the model more and more

## Social Network Modeling / Analysis

Circles = "nodes"
- people, places, groups of people, etc
Lines = "edges" or "ties"
- lines connect circles and show relationships

You can use this to create a seating chart to prevent arguments (conflict resolution):

1. Pick a person to start with and then map out all the relationships of everyone involved. Draw lines between circles (ties and nodes) to show which people dislike each other.
2. Going back to the first node, assign a color to it.
  - Keep doing this for all nodes, but **do not** assign the same color to nodes that are connected by a tie (line).
  - Reuse colors as often as you want, just don't violate the above rule
3. Once all nodes have been assigned a color, your seating arrangement is now the groups of colors!