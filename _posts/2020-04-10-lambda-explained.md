---
layout: post
title: "Lambda Explained"
---
I had my first encounter with lambda the other day when I was coding out my portfolio project and was very intrigued by it. Not going to lie, the reason was that it has a very funny name. I decided to do some investigation to get to know it a little bit more.  

## An Introduction to Lambda 

A **lambda** is a way to define a block and parameters with "= ->" syntax. 

Interestingly, defining a lambda won't run the code inside, you have to use the **call** method. 
> For example: 

{% highlight ruby %}
  my_lambda = -> { puts "This is a lambda" }
  my_lambda.call

  # "This is a lambda"
{% endhighlight %}

### Lambda can also take arguments: 

{% highlight ruby %}
  divides_by_two = ->(x) { x / 2.0 }
  divides_by_two.call(5)

  # 2.5
{% endhighlight %}
<br />
😎 Very cool. I just found a new way to type less 😏

There are also **yield** and **proc** that I want to investigate more but I'll leave that for a future date for easier digestion.  

*-Shunshun*  


<br />
