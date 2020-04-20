---
layout: post
title: "Defining Call Stack"
---
#### Short Answer: Call stack is for keeping track of multiple functions -- what is currently being run and what functions are call for within that function. 

Long answer: 

1. When script calls a function, the function gets add to the call stack.
2. Any functions that get called by the previous function gets added on top of the call stack. 
3. It starts executing the functions, after executing, the function is taken off the stack and it keeps executing through the stack. 
4. If the stack takes more space than it had assigned to it => **Stack Overflow!**

Hopefully that was informative!  😁  
-Shunshun