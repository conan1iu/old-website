---
layout: post
title:  "Integrating Github with RStudio project"
date:   2021-07-25 00:28:16 +1100
categories: ds
---

<h1><b>Why?</b></h1>

By integrating an RStudio project with Github, you can directly push changes using Git. This is extremely convenient and is actually what I used to build a website for my club, completely within R itself. And, to my observation, you can create a whole project, sync it to a new repo and when you commit+push all your new files, you may upload more than 100 files at once. 

<h1><b>Step 1: create a new Github repository</b></h1>

Go create a new repository. The `readme.md` file is optional. 

<h1><b>Step 2: enable Git in RStudio</b></h1>

1. Open your project in RStudio and follow Tools -> Version Control -> Project Setup.

2. Click on the SVN/Git tab. Select Git as the version control system. It will ask you to initialise a new Git repo and restart RStudio.

3. After Rstudio reopens, confirm that there is a Git tab in the <b>environment<b> (where you view all your objects) pane (top right by default).  

<h1><b>Step 3: synchronise with a Github repository</b></h1>

In RStudio, click on the terminal tab and start a new terminal session. Then enter:

{% highlight terminal %}
cd
{% endhighlight %}

This sets your terminal directory to home default. Then add next locations step wise. For me, I had my project on my desktop, and its name was "club". So, I would enter:

{% highlight terminal %}
cd Desktop
{% endhighlight %}

And then

{% highlight terminal %}
cd Desktop/club
{% endhighlight %}

Next, set an origin:

{% highlight terminal %}
git remote add origin https://github.com/yourUSERname/REPOname.git
{% endhighlight %}

If you added optional files into your repo, such as the `.gitignore`, `readme.md` or `license.md` file, enter

{% highlight terminal %}
git pull origin master
{% endhighlight %}

To pull them from the otherwise empty repository. If you didn't add any files, no need for this step. 

Finally, enter

{% highlight terminal %}
git push -u origin master
{% endhighlight %}

Now, you should be ready to commit files to the repository. Along the way you may have needed to sign in to your Github account and entered some keychains if on a Mac. 

<h1><b>Step 4: push files to Github from RStudio</b></h1>

In the environment pane, click on the Git tab and then click Commit. This will open a window where you can track files you made changes to. Tick all boxes for files you want to push. If you are using Github to build a website, and you have lots of files changing at once after building it to see how it looks, you can tick one box, go CMD+A and tick all of them. Write a commit message in the adjacent field and then click an up arrow to push.
