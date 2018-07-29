# Background and Literature review
## Parametric models in traditional educational research
Traditionally, research in education and educational
policies have applied similar quantitative methods to those used in the social sciences
\cite{gelman2009quantitative}, because the main goal of these
educational inquiries is to established causal effects. Parametric, sparse models which allow ease of hypothesis testing
therefore are both prevalent and important, while black-box,
flexible predictive models are not popular. \cite{teo2014handbook}

Most parametric models have prediction capability with not only point estimates
but also confidence intervals. (Meier, 2016) However, unlike causality testing, prediction and
prediction methods only take secondary roles in traditional education research,
so these models are not built to optimize for prediction power - such as
accuracy or AUC \cite{romero2010educational}.

## Recent Machine Learning methods in educational data mining
Recent advances in Machine Learning and Data Mining enable new
branches of educational research to thrive, particularly e-learning. \cite{romero2010educational}
E-learning allows new ways of generating data and new types
of data enable researchers to collect many more features of the
studied subject. Naturally, people could do a lot more with these datasets, and
they start to apply predictive machine-learning methods on them; among these
methods, ensemble methods, neural nets and SVMs are the most common. 
\cite{shahiri2015review}, \cite{amrieh2016mining} 


The body of work that apply predictive ML methods
on educational data tends to weight practicality more than interpret-ability, and
they optimize for overall prediction power instead of answering traditional
causality questions. \cite{romero2010educational, meier2016predicting}

For example, Amrieh et. al. \cite{amrieh2016mining}
apply ensemble methods on features of students collecting through an electronic
system to predict academic performance and show that even with a simple ensemble
model with minimal tuning, we can still achieve strong out-of-sample
prediction. However, the predicted values themselves do not come with useful
information that aids decision making, such as confidence intervals and
significant of contributing factors. 
\cite{efron2016computer, meier2016predicting} For example, the dataset in
\cite{amrieh2016mining} is unbalanced: Technology has 95 students
vs. Maths has 21 students, so performance prediction for a new Maths
student should be a lot less certain than that of a new Technology
student. Meanwhile, none of the ensemble models can reflect such confidence
adjustments based on their predictive values.


# Research question and proposed methodology
The previous background knowledge motivates me to investigate **if we could build
flexible predictive models in academic performance that offers the best of both
worlds - i.e. predictive
models that can achieve both meaningful confidence intervals and high
out-of-sample prediction power.** A potential research direction that I found is
using **hierarchical models** - a flexible family of parametric models that could
meet both requirements. There have
not been many studies focusing on hierarchical models in academic performance
\cite{tsai2015hierarchical, subedi2015measuring}, and there is no current study that focuses
on building a highly predictive hierarchical model first before interpreting
confidence intervals and statistical significance.

## Multi-level modeling and prediction
Multi-level modeling and prediction offer a balanced pay-off between 
predictive accuracy and interpretability \cite{gelmanbayesian,
skrondal2009prediction, kaplan2016causal} Multi-level models are particularly suitable for
educational research datasets, because education data are generally collected
from a hierarchy. For example, you can have performance scores for students in a
state, at different districts, different schools within the same district, different
class level within the same school etc. Of course, if the data are generated in
a true controlled fashion with balanced groups representation across all
covariates, then we can just do a pooled t-test, but these are survey or
longitudinal data with known biases and imbalances. \cite{konig2017bayesian}

Bayesian techniques are commonly use to fit hierarchical model is one of the
major usage of Bayesian techniques. Previously, due to
computational complexity of the sampling algorithms in these Bayesian techniques, building hierarchical models are hard.
However, recent advances in hardware and software have opened up these
techniques to a wider range of social science problems. \cite{carpenter2017stan}


## Proposed research data and methodology

### Research data
I will use the publicly available dataset that Amrieh et. al. \cite{amrieh2016mining} have kindly
shared online. I have obtained a copy so there is no risk in data
acquisition process. 
Their paper goes in sufficient details to create a random forest or a
gradient-boosted tree, so basic understanding on the dataset's completeness and
biases are also available.


### Independent/dependent variables and validity
**Independent variables** are features of students, from both registration records
(e.g. ages, subjects, gender and responsible parent's gender) and collection of
learning activities on an electronic
system (e.g. eagerness and attention). **Dependent variable** is academic
performance, i.e. a final score of course assessment, available in both
continous and categorical form. The research question therefore aims to find out
if the independent variables have any prediction power on the dependent.

**Internal validity** is addressed by the model building process with necessary
diagnostics and cautions against biases. The research builds
hierachical models with this dataset, including a re-do of
data preprocessing and features selection. Multiple hierarchies should be tested
based on suggestions from related educational studies or common known effects
(e.g. gender/grade level/topic). These models will be selected through
cross-validation and optimization of prediciton power (accuracy or AUC).

**External validity** is ensured by positioning this research within related
studies during the model building and results interpretation
processes. Conclusions from this study should have fundamental grounds in
educational-psychological theories.


# Required task list and Deliverable calendar
By week, I will list tasks that need to be completed and their descriptions.

## Week 6
Solely focus on building up knowledge on hierarchical models and its fitting
methodology. The knowledge acquisition process invoves the following tasks:

* Find relevant textbook examples and tutorials
* Setup software and acquire data
* Work through these tutorials 
* Write a summary of the avove findings in a status report

## Week 7
* Continue to acquire knowlege on hierarchical models
* Finish first end-to-end example on a simple dataset
* Build relevant analytics, graphs and interpretations of the above sample dataset
* Frovide a summary in the first intermediate milestone

### First intermediate milestone
Research methodologies overview. 

* Summarize the how-tos and pros and cons of hierarchical models.
* Present examples of building and interpreting hierarchical models on textbook
cases.

## Week 8
Start of data analysis specifically to this project. Tasks to complete:

* Obtain the publicly available dataset that Amrieh et. al. have kindly shared, 
* Create their published ensemble model.  Their paper goes in sufficient details
  to create a random forest or a gradient-boosted tree with equivalent prediction power (accuracy ~80%) to serve as a baseline.
* Work on data preprocessing and features selection to prepare this
dataset for next week's hierarchical model building. 
* Devise and submit a clearer, updated plan for week 9
* By the end of this week, I should have a detailed understanding of the targeted dataset.

## Week 9
* Follow up on week 8's revised plan
* Conduct data analysis with initial conclusions and further directions
* Replan week 10 and week 11 if needed, maybe cut back on some initial directions
  to make sure I can deliver by week 11
* Premilinary results will be summarized in the second intermediate milestone

### Second intermediate milestone
Build hierachical models with this dataset - multiple hierarchies should be tested
based on suggestions from related educational studies or common known effects
(e.g. gender/grade level/topic). These models will be selected through
cross-validation and optimization of prediciton power (accuracy or AUC). This
step is the most dificult if we aim to build a hierarchical model with high accuracy.


## Week 10
* Finalize the predictive models with appropriate graphs and early interpretations
* Write up technical report on empirical tests. I will review the overal performance that the model get, then deep-dive
  into individual predictive samples. Out-of-sample cases from unbalanced groups
  will be tested against the model and the prediction results will be analyzed to
  understand if multi-level modeling has added any value.

* Submit draft for final project for feedback including the technical report. This goal is ambitious, but it serves as early signal for me to
start wrapping things up. 
* If failing to produce a draft, then re-plan week 11 and maybe cutback to make sure I still can submit the final project.

## Week 11
* Conclude any loose end from week 10 - should take less than 30% of this week's time.
* Polish final draft to a final paper 
* Make the final presentation
* Submit the final project with all related materials

\pagebreak











