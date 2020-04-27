---
layout: post
title: "How Promise Works in JavaScript"
---
In this blog we'll look into promises in JavaScript. I feel like it's really important to really understand promises expecially as we gain more experiences with JavaScript. 

We often focus on the handling when working with promises, and a promise is often used with asynchoronous operations like API calls, DB operations or IO calls. The most important parts to understand of a promise are creating and handling. Let's start by looking into the creation of a promise: 

{% highlight javascript %}
  new Promise( function(resolve, reject) { ... } );
{% endhighlight %}

When creating a promise we pass a function that takes two params, which are in turn two functions. When a promise is complete, either a reject or resolve is called. These represents the key parts of a promise. The success of a promise is usually associated with resolve, and the faulting state is often associated with reject depending on the point of view. 

### Resolve and Reject 

Let's look at a real life example, like when a friend has made us a promise: 

{% highlight javascript %}
  const friendKeepsPromise = true;
  const friendsPromise = new Promise(function(resolve, reject) {
    if (friendKeepsPromise) {
      resolve("My friend kept their promise");
    } else {
      reject("My friend is a liar");
    }
  });

  console.log(friendsPromise)
{% endhighlight %}

<br>

In this case the promise would be resolved right away to "My friend kept their promise". Simple right?

{% highlight javascript %}
  Promise {<resolved>: "My friend kept their promise"}
         __proto__: Promise
         [[PromiseStatus]]: "resolved"
         [[PromiseValue]]: "My friend kept their promise"
{% endhighlight %}

<br>

Additionally, a promise can have two other states. The pending state for this promise would look like this:

{% highlight javascript %}
  Promise {<pending>}
         __proto__: Promise
         [[PromiseStatus]]: "pending"
         [[PromiseValue]]: undefined
{% endhighlight %}

<br>

While the rejected state would look like this:

{% highlight javascript %}
  Promise {<rejected>: "My friend is a liar"}
         __proto__: Promise
         [[PromiseStatus]]: "rejected"
         [[PromiseValue]]: "My friend is a liar"
{% endhighlight %}

<br>

### Prototypes

After a promise has been resolved or rejected, we often want to update something. This is where the prototype methods come in. When a promise is in the pending state, these three prototype methods are really handy: 

### Promise.prototype.then()
[Link to documentation](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise/then) 
<br>

Let's add a `setTimeout()` in our code to use `then()`:

{% highlight javascript %}
  const friendKeepsPromise = true;
  const friendsPromise = new Promise(function(resolve, reject) {
    setTimeout(() => {
      if (friendKeepsPromise) {
        resolve("My friend kept their promise");
      } else {
        resolve("My friend is a liar");
      }
    }, 1000);
  });

  friendsPromise.then(message => console.log(message));
{% endhighlight %}

<br>

### Promise.prototype.catch()
[Link to documentation](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise/catch) 
<br>

If a promise if rejected with an error:

{% highlight javascript %}
  const friendKeepsPromise = false;
  const friendsPromise = new Promise(function(resolve, reject) {
    setTimeout(() => {
      if (friendKeepsPromise) {
        resolve("My friend kept their promise");
      } else {
        reject(new Error("My friend is a liar"));
      }
    }, 1000);
  });

  friendsPromise.catch(error => console.log(error.message));
{% endhighlight %}

<br>

### Promise.prototype.finally()
[Link to documentation](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise/finally) 
<br>

If `.finally()` is implemented, it will call whenever a `Promise` is settled, regardless if the promise is rejected or fulfilled. Let's use it by adding a `waitingOnFriend`:

{% highlight javascript %}
  const friendKeepsPromise = Math.floor(Math.random() * 5) !== 1 ? true : false;
  let waitingOnFriend = true;
  const friendsPromise = new Promise(function(resolve, reject) {
    setTimeout(() => {
      if (friendKeepsPromise) {
        resolve("My friend kept their promise");
      } else {
        reject("My friend is a liar");
      }
    }, 1000);
  });

  friendsPromise
    .then(message => console.log(message))
    .catch(error => console.log(error))
    .finally(() => {
      waitingOnFriend = false;
    })
{% endhighlight %}

<br>

This image is really useful to me. It shows the flow of `.catch()` and `.then()`:

![Flow chart of Promise](/assets/promises.png)

Here you can see that `.catch()` and `.then()` also return a Promise, meaning they can be chained.

### In Summary: 
- Use `Promise` when handling asynchorous code 
- Always implement `.then()` and `.catch()`
- You can have multiple handlers of a promise 
- If you want code to execute disregards whether the promise is rejected or fulfilled, use `.finally()`
- Multiple promises: **[Promise.all()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise/all)** ,
**[Promise.race()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise/race)**

Thanks for reading!  
**-Shunshun**

<br>




