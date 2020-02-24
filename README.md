<img src="https://s3.amazonaws.com/devmountain/readme-logo.png" width="250" align="right">

# Project Summary

In this project, we'll provide practice JavaScript problems to help you better understand `Objects`.

## Setup

- `Fork` this repository.
- `Clone` your fork.
- Open one of the folders
- Open `./practice.js` with your code editor.
- Open `./index.html` with your browser.
- When you finish, move on to the next folder.

## Directions

Complete the required activities inside of `./practice.js` in each folder to make the spec runner pass it's tests. In order to check the progress of the spec runner, open `./SpecRunner.html` with your browser. Remember to commit and push your code often. Good luck!

If you have extra time, try to complete the remaining activites.

## Tips and Tricks

One of the biggest tools at the developer's disposal is the browser's built-in debugger. To use it, open `./index.html` with your browser. Another great tool for small and isolated pieces of code is <a href="http://www.pythontutor.com/visualize.html#">Pyton Tutor</a>. Just make sure to change the code to `JavaScript ES6`.

## Resources

### Objects

<details>

<summary> <code> Objects </code> </summary>

```js
// declare an object with properties
let car = {
  make: 'Ford',
  model: 'GT',
  year: 2019,
  // This is a method (function) on the object
  reverse() {
    return 'Backing Up! Beep! Beep! Beep!'
  },
}

// adding or updating properties with dot notation
car.miles = 100

// adding or updating properties with bracket notation
// if miles already exists on the object, this would change it's value
// if it doesn't this will set it as a key with a value of 150
car['miles'] = 150

// if a property doesn't exist on an object, it's considered undefined

car.owner === undefined // true

// A function contained in an object is called a method
// You can add functions to an object just like any other property

car.drive = function() {}

// You can invoke the method by accessing the function (method) on the object

car.reverse() // 'Backing Up! Beep! Beep! Beep!'
;-or -
  // Though the dot notation version above is more common
  car['reverse']() // 'Backing Up! Beep! Beep! Beep!'
```

</details>

<details>

<summary> <code> Object Factories </code> </summary>
 
 ```js
// Functions that return objects are called object factories
// They're a blueprint for creating a lot of objects of one type

function createCar(make, model, year) {
// the returned object has a property called make whose value is the argument passed to the make parameter above
// it's the same for model and year
return {
make: make,
model: model,
year: year
}
}

createCar('Ford', 'GT', 2006); // { make: 'Ford', model: 'GT', year: 2006 }
createCar('Tesla', 'Model S', 2019); // { make: 'Tesla', model: 'Model S', year: 2019 }

````

</details>

### Arrays

<details>

<summary> <code> Arrays </code> </summary>

```js
// declare an empty array
let myThings = [];

// declare an array with items
let myThings = ['Bike', 7, {name: 'Jeff'}, ['Catfish']]

// Arrays have index to access the contents inside
// they start at 0 and end at the length of the array - 1

myThings.length === 4 // true

myThings[0] === 'Bike' // true

myThings[3] === ['Catfish'] // true

myThings[4] === undefined // true

// if you don't know how long an array is, you can access the last value like so

myThings[myThings.length - 1] === ['Catfish'] // true

````

</details>

<details>

<summary> <code> Array Methods </code> </summary>

```js
// Arrays have many built in methods (functions) that we can use to interact with the array and it's contents
// These method's include ways to add items, remove items, sort the array, filter values, etc.
// Each method has a value that is returned when you invoke it. Some of the methods include:
```

- [Push](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/push)
- [Pop](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/pop)
- [Shift](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/shift)
- [Unshift](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/unshift)
- [Slice](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/slice)
- [Splice](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/splice)

</details>

<details>

<summary> <code> For Loops </code> </summary>

```js
// A for loop is a common pattern to use in JavaScript when you need to execute a block of code a certain number of times.

// This can be an arbitrary number of times, or more commonly when wanting to execute a block of code on each item in the array or searching an array. A typical for loop will look like the following:

for (var i = 0; i < 10; i++) {
  console.log(i)
}

/*
a for loop statement is comprised of 3 parts:

1. The iterator (count)
2. Condition (when should it stop looping)
3. Increment Expression (how should it add to the count?)
*/

// In the above example, we start our count at 0, loop as long as the count is less than 10 and add one to the count after each time the loop runs. This will log 0-9 to the console, respectively. You can swap the console log with any valid javascript and it will run 10 times

// You can change the values in the for statement to fit your needs, e.g.:

for (var i = 10; i > 0; i--) {
  console.log('The iterator is ' + i)
}

// In the above example we start at 10 and work our way down to 1 by decrementing the iterator

// A for loop to access array items

var myThings = ['Bike', 'Car', 'Hat']

for (var i = 0; i < myThings.length; i++) {
  console.log(myThings[i])
}

// In the above example we start our loop at 0 (or the first index in the array) and we loop as long as the iterator (count, i) is less than the length of myThings (remember, arrays start at 0, so the length will always be 1 larger than the last items index), add one to the iterator on each loop and look at the next item in the array. This will print 'Bike', then 'Car', then 'Hat'.
```

</details>

<details>

<summary> <code> Nesting </code> </summary>

```js
// The following will be several examples of accessing properties in normal structured data

var users = [
  { name: 'Steven', age: 26, friends: ['John', 'Kate'] },
  { name: 'Kate', age: 27, friends: ['John', 'Steven'] },
]

users[0].name === 'Steven' // true
users[1].name === 'Kate' // true
users[0].friends[1] === 'Kate' // true
users[1].friends[0] === 'John' // true

var user1 = {
  name: 'John',
  age: 33,
  appearance: {
    hairColor: 'Blonde',
    eyeColor: 'Hazel',
    height: {
      onTinder: '6ft. 4in.',
      offTinder: '6ft. 1in.',
    },
  },
}

user1.name === 'John' // true
user1.appearance.hairColor === 'Blonde' // true
user1.appearance.height // { onTinder: '6ft. 4in., offTinder: '6ft. 1in.' }
user1.appearance.height.onTinder === '6ft. 4in.' // true
```

</details>

### Callbacks

<details>

<summary> <code> Callbacks </code> </summary>

```js
// Most simply, a callback is a function that is passed as an argument to another function.
// That might look one of two ways:

// Example 1

// This is a generic function, it could be doing anything, but here it's just returning a string

function imDoingIt() {
  return 'Did it!'
}

// This next function expects a function as an argument for our cb parameter.
// Functions that receive functions as arguments are called higher-order functions.
// We know it expects a function because we're invoking cb within the functions body.
// cb is not a special keyword. Like any parameter, it's just a placeholder.
// We could call it catfish or hotdog if we wanted, but that wouldn't make a lot of sense.

function doTheThing(cb) {
  return cb()
}

// Here we invoke doTheThing, passing it the imDoingIt function's definition (that just means we didn't invoke the passed in function).
// The imDoingIt function is aliased as cb in the function above, which we then invoke in our function body.

doTheThing(imDoingIt) // the result of calling this function is 'Did it!'

// Example 2

// In this example, we do the exact same thing, except instead of using a named function (imDoingIt) we're using an anonymous function as the passed in argument to doTheThing.
// An anonymous function is just a function without a name.

function doTheThing(cb) {
  return cb()
}

doTheThing(function() {
  return 'Did it!'
})

// ------------------

// The callback pattern is often used in asynchronous programming,
// and we'll see more of that later, but here's a simple example
// (note: this is hypothetical code (pseudo code) and is for example only):

function login(processUserCbFunc) {
  let user = fetchUser() // This is a fake function that takes time to run. It will log the user in, getting the users data                            // from the server.
  // When fetchUser finishes running, we want to tell JavaScript to do something with the user's data
  processUserCbFunc(user)
}

function processUser(user) {
  return 'The logged in user is ' + user.name
}

// log the user in and when that's done, process them
login(processUser)

// --------------------

//Another common use case for the callback pattern is code reuse.
// Let's imagine you're processing bank transactions (deposits and withdrawals).
// You might write your code like this with callbacks.

// Transaction is a function that expects a dollar amount, and a callback function called action

function transaction(amt, action) {
  // rather than adding this if statement to make sure we're dealing with valid dollar amounts in both the deposit and withdraw functions below, we can write it once here.
  // This helps keep our code D-R-Y (Don't Repeat Yourself)
  if (amt <= 0) {
    return 'Please use a valid amount'
  }
  // As long as the amt is greater than 0, we'll perform our action (invoke our callback function) passing in the amt.
  return action(amt)
}

// a function that would deposit the given amount
function deposit(amt) {
  return 'You deposited $' + amt
}

// a function that would withdraw the given amount
function withdraw(amt) {
  return 'You withdrew $' + amt
}

// In these four invocations we call our transaction function with an amount,
// and a callback representing which action we want to perform with the given amounts.

transaction(100, deposit) // 'You deposited $100'

transaction(50, withdraw) // 'You withdrew $50'

transaction(-40, withdraw) // 'Please use a valid amount'

transaction(-100, deposit) // 'Please use a valid amount'

// As you can see above, callbacks provide a pattern for reusing chunks of
// code and grouping/reducing our logic (in this case our simple if statement
// that applies to both deposits and withdrawls).

// In review:

// a callback is a function passed as an argument to another functions invocation
// a higher-order function is any function that receives a function as an argument to it's invocation
// from above: transaction(deposit) => transaction would be the higher-order function and deposit would be the callback
// The callback pattern (or more simply, using callbacks in our code) allows us to write cleaner code with less repetition
// Callbacks are often used for asynchronous programming (think requesting data, logging a user in, etc.)
```

</details>

## Contributions

If you see a problem or a typo, please fork, make the necessary changes, and create a pull request so we can review your changes and merge them into the master repo and branch.

## Copyright

© DevMountain LLC, 2020. Unauthorized use and/or duplication of this material without express and written permission from DevMountain, LLC is strictly prohibited. Excerpts and links may be used, provided that full and clear credit is given to DevMountain with appropriate and specific direction to the original content.

<p align="center">
<img src="https://s3.amazonaws.com/devmountain/readme-logo.png" width="250">
</p>
```
