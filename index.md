# The R code library

**Index**
1. [Useful Packages](#1-Useful-Packages)
2. [Importing & Reading Data](#2-Importing--Reading-Data)
3. [Data Analysis](#3-Data-Analysis)
4. [Visualizing Data](#4-Visualizing-Data)
0. [Useful links](#0-Useful-links)

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
Here we are creating a dataset named "data" from the .csv file named "file". 
```
data <- 
  read_csv("file.csv", col_types = "cccd") %>% 
  mutate(
    var1 = as.factor(var1),
    var2 = as.factor(var2))
``` 

## 3. Data Analysis 
Basic regression with a linear model and two variables. 
```
reg <- lm(dv ~ iv1 * iv2, data = data)
```

Then one-way ANOVA. 
```
anova_reg <- anova(reg)
```

Formatting with the `psycho`package.
```
results_anova <- analyze(anova_reg)
print(results_anova) # APA text output
summary(results_anova) # summary table
``` 


## 4. Visualizing Data
The position dodge below ensures no overlaps on the data points in the plot, which will be included in the "position" argument. 
```
pd <- position_dodge(0.3) 
p_data <- 
  data %>% 
  ggplot(aes(x = var2, y = var1, color = var2, group = var2)) +
    stat_summary(fun.y = mean, geom = "point", shape = 18, size = 3, position = pd) + 
    stat_summary(fun.y = mean, geom = "line", position = pd) + 
    stat_summary(fun.data = mean_cl_normal, geom = "errorbar", width = 0, position = pd) + 
    ylab("Mean(time) and 95% CI (from individual group)") +
    expand_limits(y = 0)
```

## 0. Useful Links
- Chartmaker directory: http://chartmaker.visualisingdata.com/
- Colours in R: http://www.stat.columbia.edu/~tzheng/files/Rcolor.pdf
- Designing visualization: https://github.com/wxyyxc1992/Awesome-CS-Books-Warehouse/blob/master/Frontend/DataVisualization/2014-Visualization%20Analysis%20%26%20Design.pdf
- GGplot cheatsheet: https://github.com/rstudio/cheatsheets/blob/master/data-visualization-2.1.pdf
- Mathematical symbols in R markdown / LaTeX: https://oeis.org/wiki/List_of_LaTeX_mathematical_symbols

**to be continued...**
