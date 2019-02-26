R Presentations
========================================
author: Bernardo D'Auria
date: February 26th, 2018
font-family: 'Helvetica'
css: custom.css


About RPresentation
========================================

*RPresentation* is a special Markdown dialect used to create
HTML presentations.

The fale is saved with extension *.Rpres* and is compiled using 
*RMarkdown* and *knitr* packages. 

It generates two files *.md* and *.html*. The latter may be open in a general *web browser*.

Basic 
========================================
incremental: true

To write a slide just type:

    Slide Title
    ========================================
    {markdown content}
  
To change the default appearence or behaviour of a slide include
*slide commands*

    Slide Title
    ========================================
    command: value
    {markdown content}
    
Slide commands 
========================================
transition: none

Example of slides commands are:

- title: `true | false`

- type: `section | sub-section | prompt | alert`

- incremental: `true | false`

- transition: `rotate | none | linear | fade | zoom | concave`

- transition-speed: `default | slow | fast`

Slide commands 
========================================
transition: none

Example of slides commands are:

- font-import: `font_url`

- font-family: `font_family`

- class: `css_class`

- css: `css_url`


Section slide 
========================================================
type: section 

This is a *section* slide

Sub-Section slide 
========================================================
type: sub-section 

This is a *sub-section* slide

Promt slide 
========================================================
type: prompt 
incremental: false
transition: zoom

This is a *promt* slide with 
- *incremental* set to *false*, the default value
- *transition* set to *zoom*.

This is an example of *bullet* list:

- bullet 1
- bullet 2
- bullet 3

Alert slide 
========================================================
type: alert 
incremental: true
transition: fade

This is a *alert* slide with 
- *incremental* set to *true*,
- *transition* set to *fade*.

This is an example of *numbered* list:

1. item 1
2. item 2
3. item 3


Slide without title and different fonts
========================================================
title: false
font-import: http://fonts.googleapis.com/css?family=Risque
font-family: 'Risque'

This slide has
- *title* set to *false* 
- *font-import* set to <http://fonts.googleapis.com/css?family=Risque>
- *font-family* set to *'Risque'*

Slide with Code
========================================================

````
    ```{r}
    summary(cars)
    ```   
````

to get:

```r
summary(cars)
```

```
     speed           dist       
 Min.   : 4.0   Min.   :  2.00  
 1st Qu.:12.0   1st Qu.: 26.00  
 Median :15.0   Median : 36.00  
 Mean   :15.4   Mean   : 42.98  
 3rd Qu.:19.0   3rd Qu.: 56.00  
 Max.   :25.0   Max.   :120.00  
```


Slide with Code not Evaluated
========================================================

````
    ```{r, eval=FALSE}
    summary(cars)
    ```   
````

to get:

```r
summary(cars)
```

Slide with Evaluation but not Code
========================================================

````
    ```{r, echo=FALSE}
    opts_chunk$set(cache=TRUE) # to use cache
    summary(cars)
    ```   
````

to get:

```
     speed           dist       
 Min.   : 4.0   Min.   :  2.00  
 1st Qu.:12.0   1st Qu.: 26.00  
 Median :15.0   Median : 36.00  
 Mean   :15.4   Mean   : 42.98  
 3rd Qu.:19.0   3rd Qu.: 56.00  
 Max.   :25.0   Max.   :120.00  
```

Slide with Plot
========================================================



```r
fit <- lm(dist ~ 1 + speed, data = cars)
```

````
    ```{r, echo=FALSE, fig.width=12, fig.height=4}
    par(mar = c(4, 4, 1, 0.1))
    plot(cars, pch = 19, col = "darkgray")
    abline(fit, lwd = 2)
    ```   
````

![plot of chunk unnamed-chunk-5](RPresentation-figure/unnamed-chunk-5-1.png)

Slide with Image
========================================================

```markdown
 ![angry-birds](https://goo.gl/df18Vv)
```

[//]: # (orignal url: https://steemitimages.com/DQmQgpELj7e4BQnRTEHN3REcza4zfv58h8y8GrzVjUh17Fz/94740_017.jpg)

![angry-birds](https://goo.gl/df18Vv)

Slide with Two Columns
========================================================
left: 70%

````
      first column
      ```{r}
      1:10
      ```
      ***
      second column
      ```{r}
      (1:10)^2
      ```
````

first column

```r
1:10
```

```
 [1]  1  2  3  4  5  6  7  8  9 10
```
***
second column

```r
(1:10)^2
```

```
 [1]   1   4   9  16  25  36  49  64  81 100
```

Slide with Some Math
========================================================

      $$
      \int_{-\infty}^ {\infty} e^{-x^2} \, dx = \sqrt{\pi}
      $$

$$
\int_{-\infty}^ {\infty} e^{-x^2} \, dx = \sqrt{\pi}
$$

Using HTML tags
========================================================

raw HTML can be used to get special font effects, such as:
- `<small>Smaller font sentence.</small>` 

<small>Smaller font sentence.</small>
- `<span style="font-weight: bold;">Pay attention to this!</span>`

<span style="font-weight: bold;">Pay attention to this!</span>

However mixing *markdown* with *html* code may lead to non-expected results.
Try it yourself

Slide formatted with External CSS
========================================================
class: special-del

Including in the title slide the command:
    
    css: custom.css
    
with `custom.css` containing

    .reveal section del {
      color: red;
    }

we get by

    ~~this text will be red~~ 

the following formatted text 

~~this text will be red~~

However it's not **trivial** to customize by using CSS files.


References
========================================================

From **RStudio support**:
- [Authoring R Presentations](https://support.rstudio.com/hc/en-us/articles/200486468)
- [Slide Transitions and Navigation](https://support.rstudio.com/hc/en-us/articles/200714013-Slide-Transitions-and-Navigation)
- [Customizing Fonts and Appearance](https://support.rstudio.com/hc/en-us/articles/200532307)
- [Displaying and Distributing Presentations](https://support.rstudio.com/hc/en-us/articles/200714023-Displaying-and-Distributing-Presentations)

Additional references:
- R Markdown [Reference Guide](https://www.rstudio.com/wp-content/uploads/2015/03/rmarkdown-reference.pdf)
- [Presentation Ninja](https://slides.yihui.name/xaringan) made using _xaringan_ package by Yihui Xie

