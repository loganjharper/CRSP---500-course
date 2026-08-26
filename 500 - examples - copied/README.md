# 500-examples

Examples for Students in PQHS/CRSP 500 with Professor Thomas Love at CWRU

1. The [`toy` example](#the-toy-example)
2. The [`lindner` example](#the-lindner-example)
3. The [`dm2200` example](#the-dm2200-example)
4. The [`rhc` example](#the-rhc-example)

## The `toy` example

- Here is the [link to the toy example online](https://thomaselove.github.io/500-examples/toy_analysis.html), which provides both the HTML and (downloadable) Quarto files.
- The `toy` data set is found on our [500 data page](https://github.com/THOMASELOVE/500-data/blob/master/data/toy.csv).

- The Data Set is 100% fictional.
    - It contains data on 400 subjects (140 treated and 260 controls) on treatment status, six covariates, and three outcomes, with no missing observations anywhere.
    - We assume that a logical argument suggests that the square of `covA`, as well as the interactions of `covB` with `covC` and with `covD` should be related to treatment assignment, and thus should be included in our propensity model.
    - Our objective is to estimate the average causal effect of treatment (as compared to control) on each of the three outcomes, without propensity adjustment, and then with propensity matching, subclassification (stratification), weighting and regression adjustment using the propensity score.
    
## The 13 Tasks We'll Tackle in the `toy` Example

1.  Ignoring the covariate information, what is the unadjusted point estimate (and 95% confidence interval) for the effect of the     treatment on each of the three outcomes (`out1.cost`, `out2.event`, and `out3.time`)?
2.  Assume that theory suggests that the square of `covA`, as well as the interactions of `covB` with `covC` and `covB` with `covD` should be related to treatment assignment. Fit a propensity score model to the data, using the six covariates (A-F) and the three     transformations (A<sup>2</sup>, and the B-C and B-D interactions.) Plot the resulting propensity scores, by treatment group, in an     attractive and useful way. 
3.  Use Rubin's Rules to assess the overlap of the propensity scores and the individual covariates prior to the use of any propensity score adjustments.
4.  Use 1:1 greedy matching to match all 140 treated subjects to control subjects without replacement on the basis of the linear propensity for treatment. Evaluate the degree of covariate imbalance before and after propensity matching for each of the six covariates, and present the pre- and post-match standardized differences and variance ratios for the covariates, as well as the square term and interactions, as well as both the raw and linear propensity score in appropriate plots. Now, build a new data frame containing the propensity-matched sample, and use it to first check Rubin's Rules after matching.
5.  Now, use the matched sample data set to evaluate the treatment's average causal effect on each of the three outcomes. In each case, specify a point estimate (and associated 95% confidence interval) for the effect of being treated (as compared to being a control     subject) on the outcome. Compare your results to the automatic versions reported by the Matching package when you include the     outcome in the matching process.
6.  Now, instead of matching, instead subclassify the subjects into quintiles by the raw propensity score. Display the balance in terms of standardized differences by quintile for the covariates, their transformations, and the propensity score in an appropriate table or plot(s). Are you satisfied?
7.  Regardless of your answer to the previous question, use the propensity score quintile subclassification approach to find a point estimate (and 95% confidence interval) for the effect of the treatment on each outcome.
8.  Now using a reasonable propensity score weighting strategy, assess the balance of each covariate, the transformations and the linear propensity score prior to and after propensity weighting. Is the balance after weighting satisfactory?
9.  Using propensity score weighting to evaluate the treatment's effect, developing a point estimate and 95% CI for the average causal effect of treatment on each outcome.
10. Finally, use direct adjustment for the linear propensity score on the entire sample to evaluate the treatment's effect, developing a point estimate and 95% CI for each outcome.
11. Now, try a double robust approach. Weight, then adjust for linear propensity score.
12. Compare your conclusions about the average causal effect obtained in the following six ways to each other. What happens and why? Which of these methods seems most appropriate given the available information?
    - without propensity adjustment,
    - after propensity matching,
    - after propensity score subclassification,
    - after propensity score weighting,
    - after adjusting for the propensity score directly, and
    - after weighting then adjusting for the PS, to each other.
13. Perform a sensitivity analysis for your matched samples analysis and the first outcome (`out1.cost`) if it turns out to show a statistically detectable treatment effect.

## The `lindner` example

- Here is the [link to the lindner example online](https://thomaselove.github.io/500-examples/lindner_analysis.html), which provides both the HTML and (downloadable) Quarto files.
- The `lindner` data set is found on our [500 data page](https://github.com/THOMASELOVE/500-data/blob/master/data/lindner.csv).

## The `lindner` data

The `lindner` data come from an observational study of 996 patients receiving an initial Percutaneous Coronary Intervention (PCI) at Ohio Heart Health, Christ Hospital, Cincinnati in 1997 and followed for at least 6 months by the staff of the Lindner Center. The patients thought to be more severely diseased were assigned to treatment with abciximab (an expensive, high-molecular-weight IIb/IIIa cascade blocker); in fact, only 298 (29.9 percent) of patients received usual-care-alone with their initial PCI. The `lindner` data is part of the `twang` package.

The analysis provided here was developed by **Wyatt P. Bensken** and **Harry Persaud**. It involves 12 separate tasks using methods for both quantitative and binary outcomes that are analogous to those in the `toy` example developed by Professor Love. The main difference is in style, and in the fact that 1:1 matching without replacement performs very poorly.

We hope you find this helpful.

## The `dm2200` example

- Here is the [link to the dm2200 example online](https://thomaselove.github.io/500-examples/dm2200_analysis.html), which provides both the HTML and (downloadable) Quarto files.
- The `dm2200` data set is found on our [500 data page](https://github.com/THOMASELOVE/500-data/blob/master/data/dm2200.csv).

The task here is to fit propensity matches, using 8 different approaches.

## The `rhc` example

- Here is the [link to the rhc example online](https://thomaselove.github.io/500-examples/rhc_analysis.html), which provides both the HTML and (downloadable) Quarto files.
- The `rhc.csv` data set is found on our [500 data page](https://github.com/THOMASELOVE/500-data/blob/master/data/rhc.csv).
- The `rhc.Rds` data set is also found on our [500 data page](https://github.com/THOMASELOVE/500-data/blob/master/data/rhc.Rds).

This example uses real data from the SUPPORT study, describing some matching and weighting analyses related to the causal effects of right heart catheterization in critically ill patients.

Details on the SUPPORT study may be found at

- Connors Alfred F et al. 1996 [The Effectiveness of Right Heart Catheterization in the Initial Care of Critically Ill Patients](https://github.com/THOMASELOVE/500-sources/blob/main/articles/Connors%20et%20al%201996%20JAMA%20The%20Right%20Heart%20Catheterization%20Study.pdf) *Journal of the American Medical Association*, 276: 889-897.

Another article of special interest is:

- Hirano K and Imbens GW 2001 [Estimation of Causal Effects using Propensity Score Weighting: An Application to Data on Right Heart Catheterization](https://github.com/THOMASELOVE/500-sources/blob/main/articles/Hirano%20and%20Imbens%202001%20Weighting%20in%20RHC.pdf) *Health Services & Outcomes Research Methodology*, 2, 259-278.

## Another Example

1. Another propensity analysis of these data [is available here](http://rstudio-pubs-static.s3.amazonaws.com/8257_c577ba847be34e89b85a326f20b6d6b9.html). 
2. And here's [(part of) another one](https://ehsanx.github.io/SARGC-TIMethods/).

