# The R code library
## Stats 101 

**Index**
1. [Useful Packages](#1-Useful-Packages)
2. [Importing & Reading Data](#2-Importing--Reading-Data)
3. [Data Analysis](#3-Data-Analysis)
4. [Visualizing Data](#4-Visualizing-Data)
5. [Useful links](#5-Useful-links)
6. [Updates](#6-Updates)

*Sources: Most of the info below is based on or from my professor Chat Wacharamanotham's course "Quantitative Methods in Human-Computer Interaction" at the University of Zurich. With any mention of packages or functions, some text can be from their help documentation.*

## 0. Blog Updates
**Next update**: *editing and preparing data for analysis + EFA/CFA + IRT/IRC/ICC + writing the package names next to their functions + updates described in part 6 + adding useful papers in some sections for further reading*

**06.05**: This library has been extremely useful for many other classes actually! We learn all these different concepts in different classes, and sometimes it's difficult to piece it all together. I've been trying to go through my past stats/R classes to add it here to allow to have a master library that I can always consult whenever I'm doing a new research or just coding in R. I will most likely continue this library even after this class is over (minus the blog part) to use to combine all the stats knowledge I've acquired.
So, for this update I will be adding some photos/illustrations of the different graphs and generally trying to make the library more attractive. Then, I already started to add descriptions of models end of last week and this weekend, and I will continue doing so today. This mainly includes the zero-inflated models and the fixed/random effects models.   
**–>all sections: illustrations added + zero-inflated, fixed & random effects models**

**03.05** - tiny updates, totally forgot to add special variables in the ggplot section, doing it now to not forget next update ;) I was in the mood to write, so I started the next update with new function information for fixed and random effects. + small addition on the 4th on gridding. + on the 5th small addition mainly formatting.     
**->section 3, 4 & 5 updated: descriptions of regressions**

**29.04** - Instead of doing the planned update, I will share new things from today's class instead and postpone my next update. I didn't expect to have so much new material in class today, so get ready "concepts in statistics: part 2". It's mostly going to be more theoretical, with code, but that's alawys really useful to remember the correct terms and the explanations behind the code.   
**->section 3 updated: descriptions of regressions**

**23.04** - I added the full descriptions for each model, and also added a few new models that I will be describing next time. Also thought I'd add a thought process on how to actually choose a model, which is not always easy nor obvious. The questions I've written are not full-proof, but can give you a small idea of which models to consider during the analysis. Don't forget to always check up on the residuals to see how you're doing.  
I also thought that just good ol' copy-pasting of links might not be the best looking choice. So now the links have been integrated in the text to look nicer – and it does look significantly nicer. I added another technique of importing files with the function `file.choose()` which allows the user to directly search in their documents for the correct file. I've been using this in a R file that I share with a colleague at work, allowing us to simply choose the file every time instead of re-writing a path. A list of shortcuts for RStudio has also been added in the useful links. My ultimate favourite is of course the "alt" + "-" to get an automatic arrow with spaces on both sides " <- ".   
**->section 2 & 3 updated: descriptions of regression types & styling**

**17.04** - I decided to add more functions to section 3: normal, ordered and multinomial logit and probit. We use these quite often in my political science courses and I thought it would be quite useful to give a quick summary of the different regression types and their uses. Obviously, there are other uses and my explanations/descriptions are not universal. So, do beware when choosing the regressions and make sure it's appropriate for the data and the analysis. You can easily compare the results by using a regression table function such as `stargazer`or `textreg`. Also shared a new link to the book *Geocomputation with R*. This book is incredibly useful for making any type of really fancy looking maps. 
Professor showed us [this cool article](https://www.autodeskresearch.com/publications/samestats). Beware of descriptive statistics kids.   
**–>section 3 update: list of regression types, and link on maps**   
   
**12.04** - So, I'm back today with adding some more useful code and to add a bit more *oompf* and colour to my previous entries (as I misunderstood the essential blog part of this library). We didn't have class this week as it was a holiday, so I searched a bit through my past classes until I found some interesting code or functions to add here. I thought they were quite useful and would find their place here. Also, I used the `grep`function for the first time this week, and it is incredibly powerful. It allows to find or match values in a vetor, then combined with `gsub` and regular expressions to replace the values for optimal usage. I also wanted to share the function `cat` and how much better it is than `print`. As `print`has the tendency to add unnecessary spacing and create strange looking outputs, especially when mixing strings with variables, I found that `cat` would just solve all my problems. I'm never using `print` again, all hail to `cat`!   
**–>section 4 update: sharing code from past lectures and seminars on stargazer and maps**   
   
**26.03** - I came accross a something new at work, Regular Expressions. I've been using them in a data cleaning project, and I have found them to be incredibly useful. Since I did not know much (or anything) of regular expression, I did some research on it. While doing that, I came accross this very useful cheatsheet and ended up using it a lot, keeping it besoide me as I worked. Since I had been using the cheatsheet so much, I thought it would be nice to add the link here and share it too!   
**–>Useful links updated.**   
   
**22.03** -  The semester has reached it's full motion, and I didn't have so much inspiration regarding code to add. As we worked on different types of plots during class, and it was quite interesting to see how they can be used to convey different information. I tried to write down the positive and negative aspects of using each graph/plot type. This type of analysis goes hand in hand with the link "Chartmaker directory" that explains which chart to make for which sort of data. It's a great help when you're unsure about how to effectively visualise and share data. We can also see the use of different uses of the `facet_grid` function, very interesting to use it to compare and contrast different variables. [Here](https://ggplot2.tidyverse.org/reference/facet_grid.html) is the full description of how it works. You'll also find in the usefull links a cheatsheet for GGplot, which always helps to refresh one's memory. The functions there are mainly the basic ones, so once it gets more complicated, sometimes an interent search will prove more fruitful.   
**–>More details added to sections 3 and 4.**  
   
**11.03** - As mentioned in the previous entry, I still needed to annotate the code in sections 2 and 3, so you will find now more explanations. Section 4 was created, and I added a plot that we worked on during class today. The plot looks much nicer than the code written here, it clearly does not do it justice!! However, the important part of it is essentially the position dodge. In this case we have a variable with three different possible values on the x-axis. In order to avoid them overlapping if the y-axis values are too close, a position dodge allows the three dots to be side by side (slightly below the mark, on the mark and slightly above the mark). This makes the plots drastically more readable and easy to understand. I will definitely be using this for my next data visualisations!   
Then, during another class this time, I was trying to figure out how to write mathematical expressions in R Markdown, which uses LateX. I kept searching for expressions every couple of minutes, until I thought I'd look for a cheatsheet. Instead, I found a really useful page with all of the code for writing the mathematical expressions. I actually downloaded the page to keep as a reference even when I don't have internet. Now, for those you have not used these before, when writing mathematical expressions in markdown, you need to write it between single dollar signs for $*in line expressions*$ and between double dollar signs $$*for emphasised expressions*$$ that will take a new lign with centre alignment. You'll also find a pdf with all the colour names used in R, it's really useful when you already used "red", "blue" and "green" ;)   
**–>Useful links added and sections 3 and 4 updated.**   
     
**05.03** - So today I created the R code library in the context of a class at UZH, Quantitative Methods in Human-Computer Interactions. The aim is to have a nice little database/library of the useful code that one will often use in quantitative methods. So As you can see below, I decided to list the packages that the teacher shared with us. I chose to add their descriptions, and then group them into broad categories, as sometimes it can be difficult to remember all the different packages and their use. Also, little tip: if you press F1 in Rstudio while the cursor is on a function, the help will appear, that's the equivalent of typing ?*functionname* in the console. The 'others' category is for the pckages that are quite broad and didn't fully fit in one category. Then came sections 3 and 4, where I just copied the code so far. I will annotate them at a later time. Finally, I wanted to mention that it's my first time using this sort of tool, and I think it's very practical! I will definitely consider github for future projects :)  
**–>Creation of the code library with sections 1, 2, 3 and 4.**    
   
## 1. Useful Packages

#### Analysis & Regressions
- `ARTool`: The Aligned Rank Transform for nonparametric factorial ANOVAs.
- `car`: Companion to Applied Regression.
- `lawstat`: Statistical tests widely utilized in biostatistics, public policy, and law. Along with the well-known tests for equality of means and variances, randomness, measures of relative variability etc, the package contains new robust tests of symmetry, omnibus and directional tests of normality, and their graphical counterparts such as Robust QQ plot; a robust trend tests for variances etc.
- `lme4`: Fit linear and generalized linear mixed-effects models. The models and their components are represented using S4 classes and methods. 
- `lmerTest`: Provides p-values in type I, II or III anova and summary tables for lmer model fits (cf. lme4) via Satterthwaite's degrees of freedom method.
- `lsmeans`: Obtain least-squares means for linear, generalized linear, and mixed models. Compute contrasts or linear functions of least-squares means, and comparisons of slopes. Plots and compact letter displays.
- `MASS`: Functions and datasets to support Venables and Ripley, "Modern Applied Statistics with S".
- `multcomp`: Simultaneous tests and confidence intervals for general linear hypotheses in parametric models, including linear, generalized linear, linear mixed effects, and survival models.
- `nnet`: Software for feed-forward neural networks with a single hidden layer, and for multinomial log-linear models.
- `nortest`: Five omnibus tests for testing the composite hypothesis of normality.
- `psycho`: The main goal of the psycho package is to provide tools for psychologists, neuropsychologists and neuroscientists, to facilitate and speed up the time spent on data analysis.

#### Development & General use
- `devtools`: Tools to make developing R packages easier. 
- `import`: This is an alternative mechanism for importing objects from packages. The syntax allows for importing multiple objects from a package with a single command in an expressive way.
- `knitr`: Provides a general-purpose tool for dynamic report generation in R using Literate Programming techniques.
- `markdown`: Provides R bindings to the 'Sundown' 'Markdown' rendering library.

#### Plots & Visual aids 
- `cowplot`: Streamlined plot theme and plot annotations for 'ggplot2'.
- `GGally`: It extends 'ggplot2' by adding several functions to reduce the complexity of combining geometric objects with transformed data.
- `ggbeeswarm`: Provides two methods of plotting categorical scatter plots such that the arrangement of points within a category reflects the density of data at that region, and avoids over-plotting.
- `ggvis`: An implementation of an interactive grammar of graphics, taking the best parts of 'ggplot2', combining them with the reactive framework of 'shiny' and drawing web graphics using 'vega'.
- `shiny`: Makes it incredibly easy to build interactive web applications with R. Automatic "reactive" binding between inputs and outputs and extensive prebuilt widgets make it possible to build beautiful, responsive, and powerful applications with minimal effort.
- `shinydashboard`: Create dashboards with 'Shiny'. This package provides a theme on top of 'Shiny', making it easy to create attractive dashboards.
- `shinyjs`: Perform common useful JavaScript operations in Shiny apps that will greatly improve your apps without having to know any JavaScript. 

#### Others
- `assertthat`: An extension to stopifnot() that makes it easy to declare the pre and post conditions that you code should satisfy, while also producing friendly error messages so that your users know what they've done wrong.
- `broom`: Summarizes key information about statistical objects in tidy tibbles.
- `lubridate`: Functions to work with date-times and time-spans: fast and user friendly parsing of date-time data, extraction and updating of components of a date-time (years, months, days, hours, minutes, and seconds), algebraic manipulation on date-time and time-span objects. 
- `modelr`: Functions for modelling that help you seamlessly integrate modelling into a pipeline of data manipulation and visualisation.
- `tidyverse`: The 'tidyverse' is a set of packages that work in harmony because they share common data representations and 'API' design.


## 2. Importing & Reading Data
#### Importing
Here we are creating a dataset named "data" from the .csv file named "file". 
```
data <- 
  read_csv("file.csv", col_types = "cccd") %>% 
  mutate(
    var1 = as.factor(var1),
    var2 = as.factor(var2))
``` 

Also, another stylish way to import data, especially when working as a team on the same R file: allowing the user to selest the file themselves. Observe.
```
data <– read_excel(file.choose(), skip=5) %>%  # choose file on your computer
  as_tibble %>%  #construct data frame
  setNames(., c(x1, x2, etc.))  # set column names
``` 
Many different function with read.*type_of_file*() can be used. However, what I find most useful, when no mutation is necessary, is to simply go to the folder in the 'file' section in Rstudio, right click and import the data. 

#### Editing & preparing data
*Next update: numeric/character/factors/etc. classes, recoding variables, creating subsets/new datasets*

## 3. Data Analysis 
Here is a basic regression with a linear model and two variables. The independent variables (iv1 & iv2) are the regressors a.k.a. predictors, and the dependent variable (dv) is the response variable, a.k.a. the outcome variable. The * sign does both the interaction (:) and addition (+). The main effect is the mean differences mong the levels of one factore. The interaction effect occurs when the mean differences among conditions differ from what predecited from overall main effect (def. from class). 
```
reg <- lm(dv ~ iv1 * iv2, data = data)
```

#### Different regression models
Here are some different regression functions you can use, depending on the type of data you have. Also linked wikipedia articles which explain in detail each model. Don't hate on wikipedia.
- **linear model**: `lm(dv ~ iv1 + iv2, data = df)` (as explained above), can be used as a simple of multiple linear regression depending on the number of IVs used in the model. It can be used to carry out regression, single stratum analysis of variance and analysis of covariance. [Read more](https://en.wikipedia.org/wiki/Linear_regression)

- **probit model**: `glm(dv ~ iv1 + iv2, data = df, family = binomial(link = probit))` This is also a glm model, similar to the logit with a binary DV, but assumes a normal distribution of errors instead. It estimates the odds of an observation happening depending on the characteristics implented in the model. –> "**prob**ability & un**it**" [Read more](https://en.wikipedia.org/wiki/Probit_model)

- **logit model**: `glm(dv ~ iv1 + iv2, data = df, family = binomial(link = logit))` glm is used to fit generalized linear models, specified by giving a symbolic description of the linear predictor and a description of the error distribution. This is a logistic model specified by the family argument, generally used for dependent variables that are binary. It assumes a standard logistic distribution of errors, estimating the probabilities in log odds. –> "**log**istic & un**it**" [Read more](https://en.wikipedia.org/wiki/Logistic_regression)

- **ordered probit model**: `polr(dv ~ iv1 + iv2, data = df, Hess = T, method = "probit")`. Fits a logistic or probit regression model to an ordered factor response. The default logistic case is proportional odds logistic regression, after which the function is named. The same can be done with a logit model, by simply changing the method. Here "Hess" is set to `TRUE` as we want the information matrix to get standard errors. The "ordered" part of the model implies that our DV here is not binary anymore (as a probit/logit should be), and could be instead a Likert-scale, grades, etc. [Read more on probit](https://en.wikipedia.org/wiki/Ordered_probit) [or logit](https://en.wikipedia.org/wiki/Ordered_logit)

- **multinomial logit model**: `mlogit(dv ~ iv1 + iv2, data = df)`. Estimation by maximum likelihood of the multinomial logit model, with alternative-specific and/or individual specific variables. Like all multinomial models, this one also has a DV made up of non-ordered categories. [Read more](https://en.wikipedia.org/wiki/Multinomial_logistic_regression)

- **Poisson model**: `glm(dv ~ iv1 + iv2,data = df, family = "poisson")` So, we find another form of glm, this time used for count data (number of deaths, population, events etc.) or contigency tables (frequency/count in table form). It assumes that the DV has a [poisson distribution](https://en.wikipedia.org/wiki/Poisson_distribution), and that the counts are independent of each other, meaning one count will not lead directly to another. It also assumes that the variance and mean are equal. [Read more](https://en.wikipedia.org/wiki/Poisson_regression)

- **negative binomial model**: `glm.nb(dv ~ iv1 + iv2, data = df, control=glm.control(maxit=200))` A modification of the system function glm() to include estimation of the additional parameter, theta, for a Negative Binomial generalized linear model. Also used for count data, it is a mixture of the Poisson model, except does not have the variance-mean assumption, with a gamma distribution. However, different distributions are related as can be [read here](https://en.wikipedia.org/wiki/Negative_binomial_distribution#Related_distributions). [Read more on the NB distribution](https://en.wikipedia.org/wiki/Negative_binomial_distribution)

- **zero-inflated Poisson model**: `zeroinfl(dv ~ iv1 + iv2 | iv3, data = df)` a function from the `pscl` package. Here is a [great description](https://stats.idre.ucla.edu/r/dae/zip/) of how to perform the model. [Read more](https://en.wikipedia.org/wiki/Zero-inflated_model)

- **zero-inflated negative binomial model**: including both Poisson and NB. [Read more](https://en.wikipedia.org/wiki/Zero-inflated_model)

- **pooling model**: `plm(dv ~ iv1, data = df, index = c("iv2","iv3"), model = "pooling")` [Read more](https://en.wikipedia.org/wiki/Panel_analysis)

- **fixed effects model**: `scatterplot(dv ~ df$iv1|df$parameter, smooth=FALSE)` Each parameter (policy, treatment, etc.) has its own baseline response and these effects are correlated with the ivs. This controls unobservable heterogeneity in the data.  If `smooth=TRUE`, then both the mean function and variance funtions are drawn for ungrouped data, and the mean function only is drawn for grouped data, `smooth=FALSE` is neither. [Read more](https://en.wikipedia.org/wiki/Fixed_effects_model)

- **random effects modell**: Basically, each unit (countries, participants, etc.) has its own baseline response, creating one intercept (beta_0) for each unit. These individual specific effects do not correlare with the ivs. This controls unobservable heterogeneity in the data. [Read more](https://en.wikipedia.org/wiki/Random_effects_model)

- **mixed-effects model**: a.k.a. hierarchical model a.k.a. multilevel linear model `lmer(dv ~ 1 + (1 | iv1), data = df, REML = F)`. Fit a linear mixed-effects model (LMM) to data, via REML or maximum likelihood. REML reference to Restricted Expected Maximium Likelihood [Read more](https://en.wikipedia.org/wiki/Mixed_model)

#### How to choose a regression?
So, now that we have a list of regressions, how to choose the appropriate one for our data and analysis? Try to answer these questions:

1. Are you doing a regression for the first time ever in your life?
   - Yes, and I don't know anything about statistics –––> **linear**
   - No, I know 2+ things on the topic  :squirrel: ––> *go to 2)*

2. What type of DV do you have?
   - Binary. ––> *go to 4)*
   - Categories. ––> *go to 6)*
   - Continuous. ––> *go to 8)*
   - Count data. ––> *go to 3)*
   - Ordered. ––> *go to 5)*
   - Panel data. ––> *go to 7)*

3. How many zeros/0 are present in your DV?  
   - If there are no or a small proportion of zeros present:
     - If the variance is equal to the mean ––––> **Poisson**
     - If overdistribution is present, the variance is superior to the mean ––––> **Negative binomial**
   - If a large proportion of zeros are present:
     - If the variance is equal to the mean ––––> **Zero-inflated Poisson**
     - If overdistribution is present ––––> **Zero-inflated negative binomial**

4. What type of cumulative distribution function (CDF - f(\*)) do you want? / What sector are you in?
   - Standard normal distribution / economics or politcal science ––––> **Probit** 
   - Logistic distribution / health sciences ––––> **Logit** 

5. Do you prefer probit or logit?
   - Probit ––––> **Ordered probit**
   - Logit ––––> **Ordered logit**

6. Do you prefer probit or logit?
   - Probit ––––> **Multinomial probit**
   - Logit ––––> **Multinomial logit**
   
7. Are there effects over time and unique individual attributes? \*
   - Neither ––––> **(independently) Pooled**
   - No effects over time, but unique individual attributes ––––> **Fixed effects**
   - Effects over time, but no unique individual attributes ––––> **Random effects**
   - Both fixed and random effects, effects over time and unique individual attributes ––––> **Mixed effects**

8. Can you fit your data with a linear regression?
   - Yes, I can use a linear regression:
      - try this one first !OLS is prone to overfitting & sensitive to multicollinearity & outliers! ––––> **Ordinary least squares** 
      - If few observations and/or high correlation IVs ––––> **Partial least squares**
      - If large multicollinearity ––––> **Ridge** or **Lasso regression**
      - If large amount of outsliers ––––> **Least absolute deviation**
    - No, then I'll use a non-linear regression:
      - good luck :) 

* the [Durbin–Wu–Hausman test](https://en.wikipedia.org/wiki/Durbin%E2%80%93Wu%E2%80%93Hausman_test) can be used to determine if fixed or random effects is better. Also, if the difference remains unclear to you, check out this [post](https://stats.stackexchange.com/questions/4700/what-is-the-difference-between-fixed-effect-random-effect-and-mixed-effect-mode).

You can always check the residuals to see if any patterns/heteroskedasticity stand out or if they're random and all is well. Also, with the probit and logits, they give quite similar results and there are many different reasons to use one rather than the other. Some really good explanations can be found [here](https://stats.stackexchange.com/questions/20523/difference-between-logit-and-probit-models). Thank you [Jim](https://statisticsbyjim.com/regression/choosing-regression-analysis/) for your endless advice on statistics.

#### Confounding variables
This is always a tough topic, as confounding variables are often quite difficult to identify. This page I find useful to help determine if one of your variables (or more) are indeed confounding: [link](http://www.ablongman.com/graziano6e/text_site/MATERIAL/confvar.htm)

Below we can see differences between the correlations:  

![correlation](http://www.transum.org/software/SW/Scatter_Graphs/Examples.png)

#### Coefficients & regression results 
Once we have performed our regression, we obviously need to understand the results (what's the point otherwise?) SO, usual results include the (coefficient) estimates, the standard errors, t-statistic and the P value for each variable + the intercept. Here are some quick definitions of the aforementioned. 
- **coefficient**: measures the betas in our regression equation. We will have the following equation: *DV = intercept_coef + var1_coef * var1* [Read more](https://en.wikipedia.org/wiki/Linear_combination)
- **std. error**: measures the standard deviation of the sample distribution. It's calculated by dividing the std. deviation by the square root of the sample size: `sd(x)/sqrt(length(x))`. The std. error of the intercept and coefficient allows to calculate the confidence interval of the regression.  [Read more](https://en.wikipedia.org/wiki/Standard_error)
- **t-statistic** (or t-value): measures the strength of the noise/variation in the data represented in units of standard error. if t is closer to 0, there is less evidence for a significant difference, therefore as the t increases, so does the evidence. `tValue = (mean(data) - 10) / (sd(data) / sqrt(length(data)))` [Read more](https://en.wikipedia.org/wiki/T-statistic)
- **P-value**: measures the significance of the variable and either rejects the null or alternative hypothesis. It's calculated from the t-value as you can see in the manual version of the calculation: `pValue = 2 * pt(-abs(tValue), df = length(data) - 1)` [Read more](https://en.wikipedia.org/wiki/P-value)

*coming up next!*
- **R square**: Normal & adjusted
- **F-statistic**:

#### Marginal effects
This part is often forgotten during the data and model analysis. [This page](https://cran.r-project.org/web/packages/margins/vignettes/Introduction.htm) explains well how to get margianl effects in R.

#### ANOVA
The one-way ANOVA is used to compare means of multiple samples. They can be the same (null hypothesis) or different (alternative hypothesis). Assumptions: (1) observations are random, (2) data is normally distributed and (3) the populations have a normal variance (check with Levene's test)
```
anova_reg <- anova(reg)
```

Formatting with the `psycho`package.
```
results_anova <- analyze(anova_reg)
print(results_anova)  # APA text output
summary(results_anova)  # summary table
``` 
#### Factors analysis
*next update: EFA, CFA, Cronbach's alpha, eigenvalues, SEM*

#### Item response theory
*next update: IRT models, IRC, ICC*

## 4. Visualizing Data
#### types of graphs
There are many different types of plots, here are a few:
- **Beeswarm**: (+) Shows all data points for clear density. (-) Overwhelming for large datasets. Harder to read.
```
import::from(ggbeeswarm, geom_beeswarm)
ggplot(data, aes(x = var1, y = dv)) +
  geom_beeswarm(cex = 2)  # scaling for point spacing
```

- **Boxplot**: (+) Allows for easy visualisation of overall trends and quartiles. Treats large data well. (-) Does not show precise values. Assumption: data is unimodal.
```
ggplot(data, aes(x=var1, y=dv, fill=var2)) +
  geom_boxplot()
```

- **Density plot**: (+) Determine if data is normally distributed. Easy to layer onto Histogram. (-) Does not show precise values.
```
ggplot(data, aes(x=dv, y=..density.., alpha = 0.4, fill = var1)) +  # choosing fill according to var1
  geom_density()
```

- **Histogram**: (+) Simple and easy to read. (-) Not very interesting. Easily misread when error bars are added. Beware of bin width and start. Check out this [great website](http://tinlizzie.org/histograms/) for optimizing reader understanding of histograms. 
```
ggplot(data, aes(x=dv, y=..count..)) +
  geom_histogram(binwidth = 0.2)  # scaling of bars
```

- **Stacked dot**: (+) Great for small datasets. Easy to read/count dots. (-) Does not show a lot of information. Beware of bandwidth and granularity, and a stack of dots does not mean that all data points in that stack is exactly the same value. 
```
ggplot(data, aes(x=overshoots, y=..count..)) +
  geom_dotplot(dotsize = 0.4)  # scaling of dots
```

- **Violin**: Similar to box plots, but (+) shows probability density.
```
ggplot(data, aes(x=device, y=time, fill = vision)) +
  geom_violin()
```

#### Special variables
When you're setting up your plot aesthetics, sometimes you may wish to use a variable that is not directly linked to your dataset. The first special variable is `..count..`, which is the equivalent of `stat(count)` and tallies the number of occurences. Then we have the `..density..`variable which \* *drumroll* \* will show the density estimates. I tried finding other ones, but I was not successful in doing so. All I managed to find are unanswered stack overflow questions or badly answered ones, so if anyone knows anything more, I am here. Tell me please. 

#### Facetting
When one would like to compare multiple variables or graphs next to one another, it is possible to use the `grid_facet()` function. This allows to avoid layering too many graphs onto one graph and creating too much clutter. With the link below, you'll find how to create the grid you would like to have. [Read more](https://ggplot2.tidyverse.org/reference/facet_grid.html)

If you're not using ggplot or any other grob, like a simple `plot()` function, the gridExtra and other gridding function probably will not work. So you can use the `par()`function. You simply need to specify the number of rows and columns you wish to have and write the plots below. 
```
par(mfrow=c(2,2))
plot(plot1)
plot(plot2)
plot(plot3)
```

#### Position dodge
The position dodge below ensures no overlaps on the data points in the plot, which will be included in the "position" argument. 
```
pd <- position_dodge(0.3) 
ggplot(data, aes(x = var2, y = var1, color = var2, group = var2)) +
 stat_summary(fun.y = mean, geom = "point", shape = 18, size = 3, position = pd) + 
 stat_summary(fun.y = mean, geom = "line", position = pd) + 
 stat_summary(fun.data = mean_cl_normal, geom = "errorbar", width = 0, position = pd) + 
 expand_limits(y = 0)
```

#### Descriptive statistics & regression tables
Now that I have extensively shown different plot types, I think it is useful to show other types of data visualisation, without GGplot. If I ever need to present regression results or dataset statistics, I will always go for `Stargazer`tables, although `textreg` is also good. Below you can find a regression table I had used: 
```
stargazer(list(reg1, reg2, reg3, reg5),  #listing the different regressions to show side by side
          header = FALSE,  # removing the header
          no.space = TRUE,  # removing spaces between lines to allow a larger table to fit in an A4 page
          intercept.bottom = FALSE,  # placing the intercept on the first line
          model.names = FALSE,  # removing model names, only to add my own annotation below in colomn.labels
          multicolumn = FALSE,
          font.size = "footnotesize",  # many sizes available, this one allowed for more data on one page
          column.sep.width = "0pt",  # setting the space between columns to 0, to allow more data on the page
          omit.stat = "all",  # removing all statistics
          title = "Hypothesis Testing through ordered and multinomial logit in log odds",
          dep.var.labels = c("Tiers", "Tiers", "Tiers", "Tiers",  "Tier 1", "Tier 2", "Tier 2w"),
          column.labels = c("o. logit", "o. logit", "o. logit", "m. logit", "m. logit", "m. logit"),  # added below the DV labels
          covariate.labels = c("(Intercept)", "Inflows", "\\textbf{Lijphart's Index}", "\\textbf{Ideal Point}", "Gov. Effectiveness", "Rule of Law", "Democracy", "(log) GDP per capita", "(log) Population", "NATO Country", "War", "TIFA", "FTA"),  # renaming rows
          type = "latex")  # technically unnecessary, as latex is default. it is useful to have it as one can quickly write "text" to see a quick print while setting the changes
```
#### Logarithmic transformation
You will see here above that some variables have been transformed with a **natural logarithm**. Before jumping the gun and doing a superfluous log, please read the amazing words that have been written in [this stacks exchange post](https://stats.stackexchange.com/questions/298/in-linear-regression-when-is-it-appropriate-to-use-the-log-of-an-independent-va/3530#3530). No wiser words have been spoken about log transformations of variables, so read before doing anything that will drastically change your results!

#### Maps 
Another beautiful way to show data, if possible, is through a **map representation of the data**. The blog post right here is very descriptive and creates a really clean yet colourful map. I have used this one many times, as it is [my "go-to" world map guide](https://brennonborbon.wordpress.com/2017/12/16/creating-simple-world-maps-in-ggplot2/). I do however usually prefer to choose my own colours. Also, check out this website/book for other really good inspirations a guides on making beautiful maps in R: Geocomputation with R in the useful links. 

#### Residuals 
Here is a nice [blog post](https://drsimonj.svbtle.com/visualising-residuals) about visualizing residuals. I quite like this one as it puts a real emphasis on the residuals which are the furthest. The post also teaches you about useful manipulations with ggplot. 

## 5. Useful Links
- [Chartmaker directory](http://chartmaker.visualisingdata.com/): a very extensive table of data visualisation types and where/how to make them. "The Chartmaker Directory is an attempt to gather and organise a useful catalogue of references that will offer an answer to one of the most common questions in data visualisation: 'which tool do you need to make that chart?’."
- [Colours in R](http://www.stat.columbia.edu/~tzheng/files/Rcolor.pdf): a PDF of all the colour names and colours used in R. 
- [Designing visualization](https://github.com/wxyyxc1992/Awesome-CS-Books-Warehouse/blob/master/Frontend/DataVisualization/2014-Visualization%20Analysis%20%26%20Design.pdf): A free online book on visualization. THis one can get pretty complicated, so don't hesitate to start fron the start. 
- [Geocomputation with R](https://geocompr.robinlovelace.net/index.html): A free online book on drawing all possible different map styles in R. 
- [GGplot cheatsheet](https://github.com/rstudio/cheatsheets/blob/master/data-visualization-2.1.pdf): understandable on its own, just a two page cheatsheet of the main functions of ggplot.
- [GGplot cheatsheet 2](http://zevross.com/blog/2014/08/04/beautiful-plotting-in-r-a-ggplot2-cheatsheet-3/): This is a very elaborate cheat*page* with extensive descriptions of ggplot functions. 
- [GGplot guide](http://www.sthda.com/english/wiki/be-awesome-in-ggplot2-a-practical-guide-to-be-highly-effective-r-software-and-data-visualization): This is a thorough guide that starts from the most basic manipulations, yet will also show you some pretty neat tricks.
- [A Handbook of Statistical Analyses Using R](http://www.ecostat.unical.it/tarsitano/Didattica/LabStat2/Everitt.pdf): This is a great guide to help you out with most statistic questions and how to perform them in R. The first chapters are really useful for newer R users or for those that want to brush up on their knowledge. 
- [Mathematical symbols in R markdown / LaTeX](https://oeis.org/wiki/List_of_LaTeX_mathematical_symbols): If you're writing equations of any sort in a markdown file, this page is really help to learn the notations. 
- [Regular expressions cheatsheet](https://www.rstudio.com/wp-content/uploads/2016/09/RegExCheatsheet.pdf): one-page cheatsheet on regular expressions. 
- [RStudio shorcuts](https://support.rstudio.com/hc/en-us/articles/200711853-Keyboard-Shortcuts): if you want to get quite efficient in R, don't hesitate to check out the shortcuts of actions you perform often. A little knowledge goes a long way here, you can save lots of time!
- [Stargazer cheatsheet](https://www.jakeruss.com/cheatsheets/stargazer/): cheat*page* on all of the possibilities with stargazer. Any question you have has its answer here. 
- [Tidyverse style guide](https://style.tidyverse.org/index.html): Proper grammar and spelling is important in all languages, including programming languages such as R! It's good to learn the basics to have beautifully written code. 

## Updates
1.0:

