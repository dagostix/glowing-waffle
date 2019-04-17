# The R code library

**Index**
1. [Useful Packages](#1-Useful-Packages)
2. [Importing & Reading Data](#2-Importing--Reading-Data)
3. [Data Analysis](#3-Data-Analysis)
4. [Visualizing Data](#4-Visualizing-Data)
99. [Useful links](#99-Useful-links)

## 0. Blog Updates
**Next update**: descriptions to the model types will be added.

**17.04** - I decided to add more functions to section 3: normal, orderded and multinomial logit and probit. We use these quite often in my political science courses and I thought it would be quite useful to give a quick summary of the different regression types and their uses. Obviously, there are other uses and my explanations/descriptions are not universal. So, do beware when choosing the regressions and make sure it's appropriate for the data and the analysis. You can easily compare the results by using a regression table function such as `stargazer`or `textreg`.
**–>section 3 update: list of regression types**
   
**12.04** - So, I'm back today with adding some more useful code and to add a bit more *oompf* and colour to my previous entries (as I miunderstood the essential blog part of this library). We didn't have class this week as it was a holiday, so I searched a bit through my past classes until I found some interesting code or functions to add here. I thought they were quite useful and would find their place here. Also, I used the `grep`function for the first time this week, and it is incredibly powerful. It allows to find or match values in a vetor, then combined with `gsub` and regular expressions to replace the values for optimal usage. I also wanted to share the function `cat` and how much better it is than `print`. As `print`has the tendency to add unnecessary spacing and create strange looking outputs, especially when mixing strings with variables, I found that `cat`would just solve all my problems. I'm never using `print` again, all hail to `cat`!   
**–>section 4 update: sharing code from past lectures and seminars on stargazer and maps**   
   
**26.03** - I came accross a something new at work, Regular Expressions. I've been using them in a data cleaning project, and I have found them to be incredibly useful. Since I did not know much (or anything) of regular expression, I did some research on it. While doing that, I came accross this very useful cheatsheet and ended up using it a lot, keeping it besoide me as I worked. Since I had been using the cheatsheet so much, I thought it would be nice to add the link here and share it too!   
**–>Useful links updated.**   
   
**22.03** -  The semester has reached it's full motion, and I didn't have so much inspiration regarding code to add. As we worked on different types of plots during class, and it was quite interesting to see how they can be used to convey different information. I tried to write down the positive and negative aspects of using each graph/plot type. This type of analysis goes hand in hand with the link "Chartmaker directory" that explains which chart to make for which sort of data. It's a great help when you're unsure about how to effectively visualise and share data. We can also see the use of different uses of the `facet_grid` function, very interesting to use it to compare and contrast different variables. Here is the full description of how it works: https://ggplot2.tidyverse.org/reference/facet_grid.html You'll also find in the usefull links a cheatsheet for GGplot, which always helps to refresh one's memory. The functions there are mainly the basic ones, so once it gets more complicated, sometimes an interent search will prove more fruitful.   
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
Here we are creating a dataset named "data" from the .csv file named "file". 
```
data <- 
  read_csv("file.csv", col_types = "cccd") %>% 
  mutate(
    var1 = as.factor(var1),
    var2 = as.factor(var2))
``` 
Many different function with read.*type of file*() can be used. However, what I find most useful, when no mutation is necessary, is to simply go to the folder in the 'file' section in Rstudio, right click and import the data. 

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
Here are some different regression functions you can use, depending on the type of data you have. 
- **linear model**: `lm(dv ~ iv1 + iv2, data = df)` (as explained above)
- **logit model**: `glm(dv ~ iv1 + iv2, data = df, family = binomial(link = logit))`
- **probit model**: `glm(dv ~ iv1 + iv2, data = df, family = binomial(link = probit))`
- **ordered probit model**: `polr(dv ~ iv1 + iv2, data = df, Hess = T, method = "probit")`. The same can be done with a logit model, by simply changing the method. Here "Hess" is set to `TRUE`as we want the information matrix to get standard errors. 
- **multinomial model**: `multinom(dv ~ iv1 + iv2, data = df)` 
- **multinomial logit model**: `mlogit(dv ~ iv1 + iv2, data = df)`. Estimation by maximum likelihood of the multinomial logit model, with alternative-specific and/or individual specific variables.
- **Poisson model**: `glm(dv ~ iv1 + iv2,data = df, family = "poisson")`
- **negative binomial model**: `glm.nb(dv ~ iv1 + iv2, data = df, control=glm.control(maxit=200))`
- **linear mixed-effects model**: `lmer(dv ~ 1 + (1 | iv1), data = df, REML = F)`. REML reference to Restricted Expected Maximium Likelihood
- **pooling model**: `plm(dv ~ iv1, data = df, index = c("iv2","iv3"), model = "pooling")`

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

Now that I have extensively shown different plot types, I think it is useful to show other types of data visualisation, without GGplot. If I ever need to present regression results or dataset statistics, I will always go for `Stargazer`tables. Below you can find a regression table I had used: 
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
You will see here above that some variables have been transformed with a natural logarithm. Before jumping the gun and doing a superfluous log, please read the amazing words that have been written in this stacks exchange post: https://stats.stackexchange.com/questions/298/in-linear-regression-when-is-it-appropriate-to-use-the-log-of-an-independent-va/3530#3530 No wiser words have been spoken about log transformations of variables, so read before doing anything that will drastically change your results!

Another beautiful way to show data, if possible, is through a **map representation of the data**. A teacher in another class had shared with us this technique of using a map to show our data. 
```
map.world <- map_data("world")
#map_data('world') %>% group_by(region) %>% summarise() %>% print(n = Inf)

# Make sure the variable is a factor using the following:
data$var <- as.factor(data$var) 
levels(data$var) <- c("lvl1", "lvl2", "lvl3", "lvl4", "NA")

hf <- left_join(map.world, data, by = c('region' = 'Country'))

theme_map <- function(...) {
  theme_minimal() +
  theme(
    text = element_text(family = "Ubuntu Regular", color = "#22211d"),
    axis.line = element_blank(),
    axis.text.x = element_blank(),
    axis.text.y = element_blank(),
    axis.ticks = element_blank(),
    axis.title.x = element_blank(),
    axis.title.y = element_blank(),
    # panel.grid.minor = element_line(color = "#ebebe5", size = 0.2),
    panel.grid.major = element_line(color = "#ebebe5", size = 0.2),
    panel.grid.minor = element_blank(),
    plot.background = element_rect(fill = "#f5f5f2", color = NA), 
    panel.background = element_rect(fill = "#f5f5f2", color = NA), 
    legend.background = element_rect(fill = "#f5f5f2", color = NA),
    panel.border = element_blank(),
    ...
  )
}

ggplot(hf, aes(x = long, y = lat, group = group )) +
  geom_polygon(aes(fill = tier14)) + 
  labs(y = NULL, 
       x = NULL,
       title = "Figure 1: World Map", 
       subtitle = "Worldwide var by level", 
       caption = "Source: World Map") + 
  theme_map() +
  theme(title = niceFont,
        legend.position = "bottom",
        legend.text = niceFont,
        panel.border = element_blank()) +
  scale_fill_viridis(option = "D", 
                     begin = .05,
                     end = .9,
                     direction = -1, 
                     discrete = TRUE,
                     name = "Level",
                     guide = guide_legend(
                       title.position = "top",
                       direction = "horizontal",
                       keyheight = unit(2, units = "mm"))) 
```

## 99. Useful Links
- Chartmaker directory: http://chartmaker.visualisingdata.com/
- Colours in R: http://www.stat.columbia.edu/~tzheng/files/Rcolor.pdf
- Designing visualization: https://github.com/wxyyxc1992/Awesome-CS-Books-Warehouse/blob/master/Frontend/DataVisualization/2014-Visualization%20Analysis%20%26%20Design.pdf
- GGplot cheatsheet: https://github.com/rstudio/cheatsheets/blob/master/data-visualization-2.1.pdf
- Mathematical symbols in R markdown / LaTeX: https://oeis.org/wiki/List_of_LaTeX_mathematical_symbols
- Regular expressions cheatsheet: https://www.rstudio.com/wp-content/uploads/2016/09/RegExCheatsheet.pdf

**to be continued...**
