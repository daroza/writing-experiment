# Experiment
---
## Functional v. Object-Oriented Approaches

In programming one usually finds themselves taking one of two approaches to a particular problem
or structural design, _Functional_ or _Object-Oriented_. While theses two approaches are completely unique in their implementation pattern, they can be used to achieve the same result.

Let's say for example we need to write code that contains customers and a particular bank account and we needed to create some sort of interface to allow information to be properly updated securely. 

**Object-Oriented Approach**

First we would setup our classes (constructors) which we represent each party involved.

```javascript
function Account(firstName, lastName, accountId) {
    this.firstName = firstName;
    this.lastName = lastName;
    this.accountId = accountId;
    this.balance = 0;
}

Account.prototype.checkBalance = function () {
    console.log(`Account #${this.accountId} has $${this.balance} available`)
}

Account.prototype.deposit = function(amount) {
    this.balance += amount;
}

Account.prototype.withdraw = function(amount) {
    this.balance -= amount;
}

let myAccount = new Account('Ian', 'Jabour', 1234);

myAccount.deposit(500);

myAccount.withdraw(50);

myAccount.checkBalance();	// --> Account #1234 has $450 available
```

**Functional Approach**

Let's contrast this with a more functional approach.

```javascript
function setupAccount(firstName, lastName, accountId) {
    let firstName = firstName;
    let lastName = lastName;
    let accountId = accountId;
    let balance = 0;
    let method = method;
    
    return function(transaction, amount) {
		if (transaction === 'deposit') {
			balance += amount;
		} else if (transaction === 'withdraw') {
			balance -= amount;
		} else if (transaction === 'balance') {
			console.log(`Account #${this.accountId} has $${this.balance} available`)
		} else {
			console.log("Please enter a valid transaction: 'deposit', 'withdraw', 'balance'");
		}
    }
}

let myAccount = setupAccount('Ian', 'Jabour', 1234);

myAccount('deposit', 500);

myAccount('withdraw', 50);

myAccount('balance');	// --> Account #1234 has $450 available
```

Despite there difference these two approaches sufficiently acheive the desired result. Where functional programming implements closures, object-oriented programming utilized constructors.

I have found that were one pattern might more commonly be used depending on the language and the goal of the software, it can be very useful to be familiar to be comfortable in both mindsets. This is especially true in a language like Javascript becuase with ES6 adding a `Class` object-oriented syntactic sugar, the language also shines in its ability to pass in callback functions and return functions to be invoked as well. This ties into the asynchronous nature of Javascript as a whole.

In the end, it is the software that utitlize the best of both worlds that generally lives the longest and maintains the functionality over time.

Topic to learn
---

I have always felt that my eye for design was slacking. I understand that this is not a matter of being born with a certain skill-set but is something that can be learned through much rigor and practice.

I want to be able to get to the point where I can incorporate my nack for technically approaches into my design implementations, while also being able to bring some of that knowledge of design into my own technical workflow.

A piece of technology that I beleive will help me get there is Sass.

Sass is an extension of the css language that adds a programmatic approach to styling in the broweser. It adds a bunch of features that can not only speed up your workflow on the front-end, but also allow you to interact with a webpage in a unique way.

Because a browser only understands HTML, Css, and Javascript, Sass has to be processed into css, hence why it is identified as a preprocessed language.

Here are the core componenents that make up Sass and allow a developer to work more like a programmer:

_Variables_ - A way to store information that you want to reuse throughout a stylesheet. This allows our code to stay DRY and can be valuable in that when a variable is changed it can immediately take effect site-wide.

_Nesting Styles_ (similar to the way html is nested) - This is the idea that Sass lets you nest your CSS selectors in a way that has the same visual hierarchy of your HTML allowing for styles to be more semantically applied.

_Partials_ - Partials are snippets, similar to those found in templating engines, that allow for a piece of code to be applied and re-applied in various parts of a stylesheet.

_Importing Modules_ - Import is a functionality that allows us to modularize our stylesheets so that we don't end up losing track of when and where we should be adjusting our code.

_Mixins_ - Mixins are much like a function in most languages in that they allow us to pass in a parameter to a piece of code that setsup some sort of style that can be inserted whereever necessary. Because of the parameterization aspect alot of flexibility is give to the user.

_Extend/Inheritance_ - Extend is again an pattern that contributes to this idea of keep styles DRY. It allows us to create a class of sorts for a specific set of styles and setup some sort of inheritance pattern within our stylesheets. (i.e All buttons inherit from the button class).

_Operators_ - Operators simply allow use to make calculations in our stylesheets. This can be huge when trying to computer things like margin and padding on elements within your site in a responsive fashion.

Although there is much more to these concepts and the code that comes along with them, the implementation of Sass, I beleive, will provide a more enjoyable experience to any developer when working with front-end design and layout.
