---
layout: post
title: "Null Object Pattern"
---
I learned about the Null Object pattern while working on my portfolio website.

Null Object reflects a do nothing relationship. It is implemented to replace **if** check for a null value. This can be used to provide default behavior in case data is not available. 

This is a code example I used in my portfolio site: 
{% highlight ruby %}
  def current_user 
    super ||  guest_user
  end

  def guest_user
    OpenStruct.new(name: "Guest User", first_name: "Guest", last_name: "User", email: "guest@example.com")
  end
{% endhighlight %}

  The method **current_user** is the example for Null Object Pattern. It doesn't do anything unless the **current_user** doesn't exist. This way, it's way easier to change code later on because everything is organized and easy to find.

  **In conclusion**, making a method to do nothing other than to handle null objects is awesome because it is a more elegant way of coding. It makes it easier to find and change later on and if you set it in the parent file you could set it once and not worry about setting it in all the child files. 
  
  The lazy person in me is super excited to learn this so that my code in the future will be more modular and easier to maintain and change. 

  **-Shunshun**