---
layout: post 
title: "Chuck Norris Jokepedia"
---
Today I finally finished my first CLI project. It's a hilarious app that gives you facts about Chuck Norris. It's a little inappropriate/offensive sometimes but mostly it will surprise you with bursts of laughter. 

![image of the app](/assets/chucknorrisapp.png)

I had so much fun during the process! I loved seeing the final result of my app even though it's a simple CLI app. I tried my best to utilize different utilities to make my app look as good as possible. I used Ruby and SQLite3 as front and back end managing. Used REST Client to GET data from the Chuck Norris API. And I used ActiveRecord to manage model relationship in my database. 

During the process, I was typing out a lot of if-else statements because I wanted to avoid bugs that appear when users enter the wrong answer. I was like: is there a better way to do this? There's gotta be a better way. So I googled around and sure enough, there's a gem that solved my problem and more. I used this gem [TTY::Prompt](https://github.com/piotrmurach/tty-prompt) to ask questions in order to make the experience more seamless. It offers select and select_multiple so that the user doesn't even have to type their answers out. It's a great gem for building out a CLI app. You can also use it to customize your colors and mask passwords. It solved a lot of problems I would've had a hard time going around later on. 

I also got stuck on the ActiveRecord model relationships. It was a very complicated relationship. I eventually got it working after changing multiple times how my models connect. Now I can say with confidence that I understand how the basics of these ActiveRecord relationships work. 


Furthermore, I learned how to make a demo video of my app using QuickTime and Spark Video which is a pretty cool thing in itself. 

This is my demo video: 

<iframe width="560" height="315" src="https://www.youtube.com/embed/tSXT3-0okXE" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>


I am very excited about making more apps of my own! Hopefully, this was fun to read and watch :) 

**-Shunshun**

[Link to Chuck Norris Jokipedia](https://github.com/ShunshunL/Chuck-Norris-Jokepedia)

<br />