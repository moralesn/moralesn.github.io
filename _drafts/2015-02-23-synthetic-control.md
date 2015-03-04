---
layout: post
title: Synthetic Control Method
comments: True
redirect_from: "/2015-01-15-synthetic-control/"
permalink: synthetic-control
---

## Synthetic Control Method of Comparisons

The synthetic control method of comparisons (SCM) for causal inference, a non-parametric statistical technique employing an 
algorithm that creates a counterfactual unit based on a weighted combination of potential donor units that most closely approximate the
treated unit (Abadie, Diamond, and Hainmueller 2010, 2014). To illustrate, imagine we are interested in evaluating whether the five-year 
income of an employee, Jennifer, was greater as the direct result of her accepting an opportunity at another company. In order to ascertain
Jennifer is better off five years after her decision, we would want compare her five-year income to what her income would have been had she 
remained with her former employer. We can utilize the synthetic control approach to generate a second Jennifer, from a counterfactual world or
alternate reality, who never left her company. Comparing the five-year incomes of the observed- and counterfactual-world Jennifer, instead of
her colleagues' incomes, would then furnish evidence about the financial merits of her choice. This statistical technique allows us to estimate
the effect of civil conflict on consumption and economic growth relative to that of the country had it not experienced conflict.

In a synthetic control (SCM) framework, each potential counterfactual unit contributes some of the information used to generate 
the synthetic control group (Abadie, Diamond, and Hainmueller 2010). Any potential donor units to the counterfactual group must not
have received the treatment in order to be utilized as counterfactuals (Abadie and Gardeazabal 2003). The following list, shown in Appendix B,
 of counterfactual weights for each country fulfills this requirement. Once a counterfactual group is defined by the user, the synthetic control 
algorithm estimates the predicted trajectory of the outcome of interest for the generated counterfactual group (Abadie, Diamond, and Hainmueller 
2014). This empowers us to estimate the impact of civil conflict on consumption and economic growth relative to an identical counterfactual country.

###Assumptions and Weaknesses
The synthetic control approach addresses a fundamental challenge in identifying causal inference, unobserved counterfactuals (King and Zeng 2006, 
Morgan and Winship 2007), assuming SUTVA conditions hold \footnote{Assumption that the treatment value for the treated unit is stable and
is only transmitted through that unit (Morgan and Winship 2007).} The synthetic control approach exhibits transparency (Baccinni, et al. 2014),
a localized focus, and relative flexibility of information used for counterfactual construction. Typically, scholars compare across different 
units assuming randomization and homogeneity in those groups they compare against. Even when addressing randomization through statistical 
techniques like matching methods (Abadie, Diamond, and Hainmueller 2010), scholars often estimate average effects rather than the estimated 
local effects of independent variables. The synthetic control approach allows for the creation of artificial counterfactuals that address 
randomization and also the estimation of the effect for each specific unit (Abadie, Diamond, and Hainmueller 2014, Baccinni, et al. 2014). The 
approach is limited in its ability to account for endogeneity, however (Billmeier and Nannicini 2013).


## Health Care Policy

The synthetic control approach is most powerful when we are highly confident in our statistical assumptions (e.g. SUTVA) and 
we can identify the precise timing of the intervention. If we are interested in a policy intervention, such as changes in 
the healthcare regime, the synthetic control approach can be very promising. To illustrate the power of the synthetic control technique, I 
have crafted some example code with associated technical documentation. I use R to clean and manipulate the data into a tidy format. I then
select   as our primary unit of interest. We can look at the   and determine that the intervention in    occured in    . 


I identify those   that are outside of the reach of the adopted policy. These    were not subject to this policy througout the time period of interest, mainly  .

We can then select the donor units we are to include in the main synth algorythm. This is done by attaching a vector with the integer identifiers for each
 belonging to a donor unit. Once we specifiy the donor units that will contribute a weighted combination of the estimated outcome for the cunterfactual
, we can employ the algorytm with the -synth- command in R. 



The resulting graphical output below illustrates the appealing nature of the synthetic control approach. We can see that the actual and counterfactual paths
remain identical prior to the adoption of the policy but diverge in its immediate aftermath. 


The syhtetic control approach is also transparent, as we can observe the weighted contribution of each donor unit to the counterfactual. 

Estimating the average of the local treatment effect (LATE) of the adoption of   policy on    , I find that for    case the estimated effect is approximately  . This is subtantial when considering . To 
learn more, you can find the code and files for this healthcare policy example [here](). 

## Economic Cost of Conflict

Healthcare policy is not the sole domain where this statistical technique can be useful. I recently led a research project that focuses on the 
estimation of the economic costs of conflict employing a synthetic control approach with co-author [Quan Li](). Below is the abstract and a copy
is available upon request:

Despite the enormous costs of conflict in terms of financial burden, resource depletion, and lost of human life, the welfare implications 
of conflict remain understudied. Given its policy relevance, we explore the economic impact of conflict employing an increasingly employed 
statistical technique to identify the impact of civil conflict on the economy. Employing a synthetic control approach, we  compare the consumption
and economic growth paths of countries that have faced civil conflict relative to a world without civil conflict. Thus, we are able to determine 
the estimated difference between the actual and counterfactual consumption and growth paths of several countries between 1960 and 2010. Our 
findings suggest that civil conflict, especially in its immediate aftermath, can have a palpable impact on the economic welfare of a country.

{% include socialmedia_plug.html %}
