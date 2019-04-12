# The R code library

**Index**
1. [Useful Packages](#1-Useful-Packages)
2. [Importing & Reading Data](#2-Importing--Reading-Data)
3. [Data Analysis](#3-Data-Analysis)
4. [Visualizing Data](#4-Visualizing-Data)
99. [Useful links](#99-Useful-links)

## 0. Blog Updates
**12.04** - So, I'm back today with adding some more useful code and to add a bit more oompf to my previous entries. We didn't have class this week as it was a holiday, so I surfed a bit until I found some interesting code or functions to add here. Some I have also taken from other classes, as I thought they were quite useful and would find their place here. 
**26.03** - Useful links updated  
**22.03** - More details added to sections 3 and 4.  
**11.03** - As mentioned in the previous entry, I still needed to annotate the code in sections 2 and 3, so you will find now more explanations. Section 4 was created, we worked on different types of plots during class, and it was quite interesting to see how they can be used to convey different information. I tried to write down the positive and negative aspects of using each graph/plot type.   
      –>Useful links added and sections 3 and 4 updated.  
     
**05.03** - So today I created the R code library in the context of a class at UZH, Quantitative Methods in Human-Computer Interactions. The aim is to have a nice little database/library of the useful code that one will often use in quantitative methods. So As you can see below, I decided to list the packages that the teacher shared with us. I chose to add their descriptions, and then group them into broad categories, as sometimes it can be difficult to remember all the different packages and their use. Also, little tip: if you press cmd + F1 (on macs) in Rstudio while the cursor is on a function, the help will appear, that's the equivalent of typing ?*functionname* in the console. The 'others' category is for the pckages that are quite broad and didn't fully fit in one category. Then came sections 3 and 4, where I just copied the code so far. I will annotate them at a later time. Finally, I wanted to mention that it's my first time using this sort of tool, and I think it's very practical! I will definitely consider github for future projects :)  
      –>Creation of the code library with sections 1, 2, 3 and 4.   

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
Basic regression with a linear model and two variables. The * sign does both the interaction (:) and addition (+).
```
reg <- lm(dv ~ iv1 * iv2, data = data)
```

Then one-way ANOVA – used to compare means of multiple samples. They can be the same (null hypothesis) or different (alternative hypothesis). Assumptions: (1) observations are random, (2) data is normally distributed and (3) the populations have a normal variance (check with Levene's test)
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
There are many different types of plots, here are a few:
- **Beeswarm**: (+) Shows all data points for clear density. (-) Overwhelming for large datasets. Harder to read.
```
import::from(ggbeeswarm, geom_beeswarm)
ggplot(data, aes(x = var1, y = dv)) +
  geom_beeswarm(cex = 2) +  # scaling for point spacing
  facet_grid(. ~ var2) +  # creating grid for different var2
  theme(legend.position = "none")
```

- **Boxplot**: (+) Allows for easy visualisation of overall trends and quartiles. Treats large data well. (-) Does not show precise values.
```
ggplot(data, aes(x=var1, y=dv, fill=var2)) +
  geom_boxplot() +
  theme(legend.position = "none")
```

- **Density plot**: (+) Determine if data is normally distributed. Easy to layer onto Histogram. (-) Does not show precise values.
```
ggplot(data, aes(x=dv, y=..density.., alpha = 0.4, fill = var1)) +  # choosing fill according to var1
  geom_density() +
  facet_grid(var2 ~ .)+
  theme(legend.position = "none")
```

- **Histogram**: (+) Simple and easy to read. (-) Not very interesting. Easily misread when error bars are added. 
```
ggplot(data, aes(x=dv, y=..count..)) +
  geom_histogram(binwidth = 0.2) +  # scaling of bars
  facet_grid(var2 ~ var1)
```

- **Stacked dot**: (+) Great for small datasets. Easy to read/count dots. (-) Does not show a lot of information.
```
ggplot(data, aes(x=overshoots, y=..count..)) +
  geom_dotplot(dotsize = 0.4) +  # sclaing of dot
  facet_grid(vision ~ device)+
  theme(legend.position = "none")
```

- **Violin**: Similar to box plots, but (+) shows probability density.
```
ggplot(data, aes(x=device, y=time, fill = vision)) +
  geom_violin() +
  facet_grid(. ~ data$vision)+
  theme(legend.position = "none")
```

The position dodge below ensures no overlaps on the data points in the plot, which will be included in the "position" argument. 
```
pd <- position_dodge(0.3) 
ggplot(data, aes(x = var2, y = var1, color = var2, group = var2)) +
 stat_summary(fun.y = mean, geom = "point", shape = 18, size = 3, position = pd) + 
 stat_summary(fun.y = mean, geom = "line", position = pd) + 
 stat_summary(fun.data = mean_cl_normal, geom = "errorbar", width = 0, position = pd) + 
 expand_limits(y = 0)
```

## 99. Useful Links
- Chartmaker directory: http://chartmaker.visualisingdata.com/
- Colours in R: http://www.stat.columbia.edu/~tzheng/files/Rcolor.pdf
- Designing visualization: https://github.com/wxyyxc1992/Awesome-CS-Books-Warehouse/blob/master/Frontend/DataVisualization/2014-Visualization%20Analysis%20%26%20Design.pdf
- GGplot cheatsheet: https://github.com/rstudio/cheatsheets/blob/master/data-visualization-2.1.pdf
- Mathematical symbols in R markdown / LaTeX: https://oeis.org/wiki/List_of_LaTeX_mathematical_symbols
- Regular expressions cheatsheet: https://www.rstudio.com/wp-content/uploads/2016/09/RegExCheatsheet.pdf

**to be continued...**
