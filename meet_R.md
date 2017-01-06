<style>
.footer {
    color: #434343;
    background: #ffffffff;
    position: fixed;
    top: 90%;
    text-align: left;
    width: 100%;
}
.header {
    color: black;
    background: #E8E8E8;
    position: fixed;
    bottom: 90%;
    text-align:center;
    width:100%;
}
.small-code pre code {
  font-size: 0.9em;
</style>

introduction to R
========================================================
author: 
autosize: true
font-family: 'Arial'


everything in a script
========================================================
title: false
<span style="font-weight:bold; font-size:1.25em; color:#ff9900;">everything in a script</span>

- <small>The most basic principle for reproducible research is: do everything via code</small>
- <small>Downloading data from the web, converting an Excel file to CSV,
renaming columns/variables, omitting bad samples or data points...do all of this with scripts.</small>
- <small>You may be tempted to open up a data file and hand-edit. But if you get a revised version of that file, you’ll need to do it again. And it’ll be harder to figure out what it was that you did.</small>
- <small>Some things are more cumbersome via code, but in the long run you’ll save time.</small>

<div class="footer" style=font-size:75%;">Attribution: Steps toward reproducible research, Karl Broman, Biostatistics & Medical Informatics Univ. Wisconsin–Madison, kbroman.org, github.com/kbroman, @kwbroman, Slides: bit.ly/jsm2016
</div>


learn a language. any language, just do it
========================================================
title: false

<span style="font-weight:bold; font-size:1.25em; color:#ff9900;">learn a language. any language, just do it</span>

<div style="margin-left:150px; margin-top:100px;">
  <img src="./images/rlogo.jpg" style="background-color:transparent; border:0px; box-shadow:none;"></img>
</div>

<div style="margin-left:800px; margin-top:-275px;">
  <img src="./images/python-logo.png" style="background-color:transparent; border:0px; box-shadow:none;"></img>
</div>


What is R?
========================================================

R is a *programming language designed for statistical computing*. Notable characteristics include:

-   vast capabilities, wide range of statistical and graphical techniques
-   very popular in academia, growing popularity in business
-   written primarily by statisticians
-   free (no cost, open source)
-   outstanding community support: mailing list, blogs, tutorials
-   easy to extend by writing new functions

<div class="footer" style=font-size:75%;">Attribution: http://tutorials.iq.harvard.edu/R/Rintro/Rintro.htm</div>


the utility of R
========================================================

It is free and popular, but what makes R worth learning? In a word: "packages". If you have a data manipulation, analysis or visualization task, chances are good that there is an R package for that. 

For example:

<div class="footer" style=font-size:75%;">Attribution: http://tutorials.iq.harvard.edu/R/Rintro/Rintro.htm</div>


the utility of R
========================================================
class: small-code

-   want to map the folks that created this slide?


```r
  library(ggmap)
  nwbuilding <- geocode("1737 Cambridge Street Cambridge, MA 02138", source = "google") 
  ggmap(get_map("Cambridge, MA", zoom = 15)) + 
    geom_point(data=nwbuilding, size = 7, shape = 13, color = "red")
```

<img src="meet_R-figure/unnamed-chunk-1-1.png" title="plot of chunk unnamed-chunk-1" alt="plot of chunk unnamed-chunk-1" style="display: block; margin: auto;" />

<div class="footer" style=font-size:75%;">Attribution: http://tutorials.iq.<br/>harvard.edu/R/Rintro/Rintro.htm</div>


the utility of R
========================================================
class: small-code

-   want to forecast the population of Australia?


```r
  library(forecast)
  fit <- auto.arima(austres)
  ## Projected numbers (in thousands) of Australian residents
  plot(forecast(fit), xlim=c(1985,1995), ylim=c(15000,19000))
```

<img src="meet_R-figure/unnamed-chunk-2-1.png" title="plot of chunk unnamed-chunk-2" alt="plot of chunk unnamed-chunk-2" style="display: block; margin: auto;" />

<div class="footer" style=font-size:75%;">Attribution: http://tutorials.iq.<br/>harvard.edu/R/Rintro/Rintro.htm</div>


the utility of R
========================================================

- create this presentation

Whatever you are trying to do, you are probably not the first to try doing it R. Chances are that someone has already written a package for that.


interacting with R
================================

the classic approach was to run R in a console