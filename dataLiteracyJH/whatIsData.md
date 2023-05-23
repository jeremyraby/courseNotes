# What is data?

## Good Hypotheses

5 Characteristics of good hypotheses:

1. Positive, not normative
  - Describes how the world is, not how it should be
    - Normative: waterboarding is unjust | Positive: waterboarding produces false testimonies
2. Has observable implications / is empirical
  - "empirical" comes from the Greek word "empeirikos" meaning "experienced"
3. Testable / falsibiable
  - Is it possible to be incorrect? If yes, it's probably a good hypothesis.
4. Generalizable
5. Parsiomonious
  - Doesn't contain irrelevant parts
    - there's no reason to expect eye color to affect voting behavior, as opposed to education level

A hypothesis is a system of concepts & arguments that work together to explain a phenomenon through causation. Establishing causation requires meeting 3 conditions:

1. Two concepts must be correlated
  - X & Y are observed together
  - Under certain conditions
2. The causing concept must occur before the other concept
  - A happens, then B happens
3. Explains the cause-effect relationship of the phenomenon better than other explanations
  - rejects alternative hypotheses, including chance

X is the independent variable, Y the dependent variable. The logical argument(s) explaining under what condition(s) X causes Y is the hypothesis. The conditions allowing X to cause Y are "constraints" and determine how/what/when/where/why X can cause Y.

## Causality

All causal research questions have a factual outcome and a counterfactual outcome. The causal effect is the difference between the two.

The factual outcome is what is actually observed following the intervention, while the counterfactual outcome, which cannot be observed, is what would have happened if the intervention had not taken place.

### Estimating a causal effect

Research question: what is the effect of drinking coffee on health?

Variables in the causal effect equation:

Units of analysis (i): individuals (rows in a dataset)
Treatment/intervention variable (X): the treatment (coffee)
Treatment units(Xi): individuals in the treatment group (Xi = 1)
Control units: individuals in the control group (given water) (Xi = 0)
Outcome variable (Y): measure of treatment effect (a health score 0-100)

There are only two possible outcomes for each unit (individual):
Yi(Xi=1) OR Yi(Xi=0)

Control groups allow us to estimate what the counterfactual is, leading us to the equation
Yi(Xi=1) - Yi(Xi=0) --> Yi(1) - Yi(0)

You will only observe one outcome for each individual because they're either in the treatment group or the control group.

Counterfactuals can only be studied/estimated for immutable variables like sex or race.

Can have "effect modifiers" (which alter the effect of the treatment when present) or "effect mediators" (which is affected by the treatment *and then* affects the outcome).

### Confounders

If a sample isn't randomly selected from a population, confounders may affect the outcome of the study. A confounder is any condition which may accompany the condition of study, eg sugar consumption may affect the health outcomes in a study about how coffee consumption affects health. Ensuring the study is free of selection bias by randomly assigning individuals to eithe the treatment or control groups, as opposed to letting the participants choose or being specifically chosen by the researcher, will reduce the chances of such confounders affecting the study's outcomes.

### Randomized controlled trials (RCTs)

Detailed info about they why/what is/how to of RCTs can be found [here](https://obgyn.onlinelibrary.wiley.com/doi/full/10.1111/aogs.13309)

The "gold" standard of experiments
- Also more readily used in sytematic reviews/meta-analyses/Cochrane reviews

One way to critique an RCT is to assess the study's validity. RCTs often have high internaal validity (intrinsic to the study) because they are performed under tightly controlled environments but may have low external validity because they may not be generalizable to a broader population due to the conditions leading to their high internal valiidty. 

Conditions affecting internal validity include sampling bias, the Hawthorne effect (observing a system changes the system), among others.

Conditions affecting external validity include not having a representative sample or even an unrepresentative study environment (lab studies vs field studies).

"Pretreatment conditions" must also be highly similar or exact for the treatment and control groups. Ie, the participants should be as similar to each other as possible to elimnate the affect of confounding variables.

#### Good research questions

5 elements of a good research question

1. *P*opulation of interest
2. *I*ntervention to study
3. *C*omparator (control)
4. *O*utcome
5. *T*ime (is there an amount of time necessary for I to cause O?)

Bad question: Does administration of tranexamic acid prevent postpartum hemorrhage?
Good question: Does 1.0 g of intravenous tranexamic acid given 4 h prior (*I*) to elective cesarean (*P*) section compared with placebo (*C*) reduce postpartum hemorrhage diagnosed as estimated blood loss of >500 mL within 24 h of birth (*O*)?

#### General Methodology

Participants are screened (inclusion criteria) to ensure they all have the same or very similar "pretreatment" or baseline conditions so as to eliminate confounders.

Participants are randomly selected (multiple ways to do this).

When possible, experiments should be blinded

- Single blind = participants don't know if in treatment or control group
- Double blind = neither researchers nor participants know if in treatment or control
- Unlabled study = Blinding may not be possible, ie participants know if they have a surgical intervention and the researchers most probably can at least surmise it. The study can still be valid, but should be reported as unlabeled

Treat all individuals the same except for the treatment (part of ensuring it's a well-controlled study)

Ensure you have a large enough sample (that isn't too large) and determine an appropriate power of the study (p-value)

Specific methods must be ethical and approved by independent committee

> Placebo may be unethical if a safe & effective treatment has already been identified, as in current HIV studies, because doing so would expose the control group to unnecessary levels of risk while denying them a safe & effective treatment.

Interim analysis may be prudent to ensure the same is actually large enough (your study is adequately powered) or the treatment is proving early on to be either no good or good

- The sample can be expanded
- If the treatment is obviously no good you may be wasting resources
- If the treatments is obviously good you may be unethically prolonging the study and denying people treatment

> Pretreatment conditions may be reported (possibly required by the publisher). If so, also reporting p-values is redundant as any observed differences must necessarily be caused by the treatment.

#### Interpretation

Check for [signifigance and magnitude](https://www.matthewbcourtney.com/post/significance-vs-magnitude-how-to-interpret-statistics-for-decision-making)
- Statistical signifigance describes the probablity the outcome is caused by chance (5%, 1% or 0.01% probability of chance)
  - measured as the p-value and is generally accepted as p < 0.05, but the study may be powered to a p < 0.01 or p < 0.001
- Magnitude, aka "practical" or "clinical" signifigance or "effect size", quantifies the differences between the treatment and control groups in real numbers
  - measured by "Cohen's d"
    - ((avgT - avgC)/std dev), where T = treatment and C = control
    - small effect: d <= 0.20
    - medium effect: d <= 0.50
    - large effect: d >= 0.80

> Outcomes can be statistically significant but not clinically significant. If the the reverse is true, the study is underpowered (sample is too small).

### Observational Studies

Tend to have lower internal validity and higher external validity than RCTs due to the fact they often can't be tightly controlled in a lab setting
