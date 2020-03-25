---
layout: post
title: "How to escape git merge message"
---
I got stuck in the terminal today and was forced to restart it because when I tried to merge my latest changes Git told me I need to pull my master branch down. And when I did, this happened:

![image of the terminal](/assets/merge_message.png)
I had never seen this before and I tried to type q/quit/enter. None of them worked. I turned to my good friend Google and googled around for a bit. And I realized it's a process to escape this state. Here's what I found:

**If you want to enter your own merge message you need to follow these two steps before the next:**
1. Press 'i' on your keyboard
2. Write your merge message

**If you want to skip the merge message or you are finished writing your own merge message:**
3. Press 'esc' (escape)
4. Write ":wq"
5. Then hit 'enter'


*Hope that was informative and help solved your issue! :)*  
*-Shunshun*

<br/>  
