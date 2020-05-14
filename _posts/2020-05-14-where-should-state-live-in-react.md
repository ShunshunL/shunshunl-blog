---
layout: post
title: "Where Should State Live in React"
---
It's definitely challenging to fully grasp where the state in React should live. React is all about the unidirectional data flow. 

### This is what I gathered: 
For each state: 
- Find out what component will use this state
- Find the common parent component
- Either this common parent or some other component higher up should own the state 

Tips: If you can't seem to find a component where it would make sense to hold the state, make another component solely for the purpose of holding that state, then add it somewhere in the hierarchy above the common parent component.

Hopefully that made state in React easier to understand! 😃  
-Shunshun