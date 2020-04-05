---
layout: post 
title: "Variable Scope in Ruby"
---
I had this question in my head today when I was coding up my first CLI application: What variable do I need based on the scope needed? 

*The narrowest the better. Right?*

But what are some examples that would make this theory more actionable?

### Local Variable Scope 

This have the narrowest scope: 

{% highlight ruby %}
a = 50

def money 
  a = 80 
  puts a #This will return 80
end 
{% endhighlight %}

**Local variable** basically means it won't look at outside the method. When the method finishes executing, you won't be able to access the variables inside anymore.

### Instance Variable Scope 

This have a wider scope: 

{% highlight ruby %}
class Money 
  def more_money 
    @quantity = 80 
  end 

  def less_money 
    @quantity = 50 
  end 
end 
{% endhighlight %}

Here, `@quantity` is shared between both methods.

Essentially, `@quantity` is only living in this class. 

### Block Scope

* Local variables created in the blocks are not avaliable outside them.
* Variables created outside the blocks can be accessed and overridden within the blocks.

I think I understood more about scopes after writing this blog. It solidified some of my disconnected knowledge pieces. Everything seems pretty intuitive now. Hope that was useful to you as well.

*-Shunshun*

<br />

  
