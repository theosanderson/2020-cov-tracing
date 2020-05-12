# Mass-testing may contribute to controlling COVID-19

**TLDR:** although a previous model has suggested mass-testing to be ineffective in controlling COVID-19, if we adjust the parameter for the scale of testing, and combine the approach with contact tracing, the model predicts that R can be reduced below 1 without social distancing.

<hr>

This is a fork of https://github.com/adamkucharski/2020-cov-tracing which is the code that contains the analysis performed in *[Effectiveness of isolation, testing, contact tracing and physical distancing on reducing transmission of SARS-CoV-2 in different settings](https://www.medrxiv.org/content/10.1101/2020.04.23.20077024v1)* by Adam J Kucharski, Petra Klepac, Andrew Conlan, Stephen M Kissler, Maria Tang, Hannah Fry, Julia Gog, John Edmunds and the CMMID COVID-19 Working Group.

As part of their paper, the authors investigate many measures for controlling COVID transmission, including **mass-testing**. A reader of the paper might conclude that mass-testing has little to offer in terms of controlling COVID, since the paper argues that R<sub>eff</sub> is 2.6 without any control measures, and almost the same (2.5) with mass-testing.

## Assumptions and conclusions of Kucharski *et al.*
The paper models mass-testing only in the following scenario:
 - 5% of the population is tested per week
 - when positive cases are identified by mass-testing no attempt is made to isolate or trace their contacts
 
 
The paper concludes that mass-testing can contribute little. The only scenario modelled that offers an R<sub>eff</sub> below 1 requires manual contact tracing, isolation of symptomatic people, and **substantial social distancing** (only 4 contacts per day allowed outside of school/work). This achieves an R<sub>eff</sub> of around 0.93.


## Changes made here

Here we have made two [small changes](https://github.com/adamkucharski/2020-cov-tracing/compare/master...theosanderson:master) to the code to enhance the effectiveness of mass-testing. Firstly we substantially increase the proportion of the population that can be tested each week, from 5% to 37%. This is based on a [proposal for mass-decentralised testing in schools and workplaces](http://theo.io/blog/2020/04/19/community-testing-for-covid-19-reaching-25-million-tests-per-week/).

Secondly, we **attempt** to add isolation and manual contact-tracing to the model alongside the mass-testing intervention. It seems perverse to perform mass-testing and then fail to trace the contacts of people identified through it, many of whom will be in the pre-infectious incubation phase.

**We are not convinced we have adequately modelled the full effect of quarantining the contacts of anyone who tests positive under mass-testing** (see [issue #1](https://github.com/theosanderson/2020-cov-tracing/issues/1)). Nevertheless, the two changes made here result in an R<sub>eff</sub> of 0.92, lower than any of the other scenarios and without the need for social distancing.


## Conclusions

If we are more optimistic about the ability to perform mass-testing, and we are prepared to pair it with contact tracing and isolation, then mass-testing may have a role to play in controlling COVID-19, which enabling life to largely proceed as normal.

## Credit

99.99% of this code is by the original authors. This re-analysis is only possible because they have made their code available.

## Warning

This has been put together by a non-expert. Corrections are welcome.
