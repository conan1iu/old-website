---
layout: post
title:  "Extracting code chunks from RSweave/Rmd file"
date:   2022-02-11 00:28:16 +1100
categories: ds
---

<h1><b>Why?</b></h1>

Sometimes when I write a report in RSweave, I will have a normal .R file on the side to test out code that I will need in the report. However, I also lose discipline at times and I end up completing all code within the RSweave file anyway. At times when I just want to upload the code to Github, I need a quick way to extract all code chunks.   

<h1><b>Step 1: set working directory to where the base file is</b></h1>

{% highlight R %}
getwd()
setwd(...)
{% endhighlight %}

<h1><b>Step 2: set object as file name</b></h1>

{% highlight R %}
a <- 'yourfilename.Rnw'
{% endhighlight %}

NB: the base file name must be unique within the working directory. So in the case of RSweave files, where (as it uses LaTeX) after generating a report a bunch of other files with the same base name (but different extensions) are produced, you will need to rename the RSweave file to something completely different and unique. 

<h1><b>Step 3: see below commands</b></h1>

For files operating under knitr, use "purl". Otherwise use "Stangle" for RSweave variants. 

{% highlight R %}
knitr::purl(a)
{% endhighlight %}

{% highlight R %}
Stangle(a)
{% endhighlight %}
