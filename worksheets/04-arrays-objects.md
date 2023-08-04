# Arrays and objects

## The concept

So we've seen that Javascript can manipulate things like words and numbers but often we'll find that we actually want to collect those kinds of things into collections. There are two broad concepts here: arrays and objects. Arrays are essentially lists of items (we call each item an element) and objects are structures that can hold a set of key-value pairs (like a car could have key-values including manufacturer, model, colour, etc - we call each of these properties). Therefore, many values can be stored in a single object variable, much like an array. However, instead of using an index to find a value, the name of the property can be used.

Let's start with arrays...

## Creating an array

The easiest way to create a JavaScript array is using square brackets `[...]` also known as an array literal. Let's create an array called `cars` which stores the names of some car makes. Write this in your `script.js` file.

```JS
var cars = ['toyota', 'suzuki', 'bmw', 'peugeot', 'jaguar'];
```

Each value in the array has an index which tells you where in the array the value is stored. We need to remember that in JavaScript that the first index is always zero. The statement `array[index]` will give you the value located at that index in the array.

So for example you can use `cars[1]` to find the 2nd value in your cars array.

### Challenge

Log to the console the 1st value from the array (clue: which index does JavaScript start at?)

## Looping through arrays

### For loop

We’ve so far used code to find and log to the console single values from the array. If an array is small enough, it would be quite easy to find out many or all the values in an array using the same code repeated but changing each index. However, this would be much less efficient for larger arrays.

A conditional `for` loop can be used to apply methods to multiple values in an array.

```JS
for (var i = 0; i < 5; i++) {
   // code block to be executed
}
```

Let's break this down a bit. Inside the `( )` we set up the loop using the variable `i` to control it, using three statements, separated by semi-colons (`;`).

- The first statement `i = 0` declares `i` (notice we don't need `var` here) and sets it to the value it should start with (this will nearly always be 0).
- The second statement `i < 5` indicates the condition(s) in which the loop will run. This is checked each time before we run the code inside the `{ }`. Whilst it resolves to `true` the loop will keep going round. The first time it resolves to `false` it will not run again.
- The third statement `i++` increases the value of the variable `i` by 1 each time the code block in the loop is executed.

Then we can put code inside the loop, between the `{ }`. We would need to use `i` as an array index to access the array value - like `cars[i]`. So the first time round the loop this would be the same as `cars[0]`, second time `cars[1]` and so on and the last time would be `cars[4]`.

For for loop acts like this set of instructions:

> **Note**: this isn't real code… don't try and copy and paste it!

```
1  Set i to 0
2  If i is less than 5...
3      // Run the code to be executed
4      add 1 to i
5      Loop back to line 2
```

Writing code out like this is called writing pseudocode. It can be very useful to write down ideas like this, without needing to worry about a computer understanding them.

### For..in loop

For an array there is an alternative way to loop through all the contents as shown below. `array` would need to be the name of the array you are looping around and then `item` would be the individual item in the array. This will run the code block for each item in the array.

```JS
for (item of array) {
  // code block to be executed
}
```

### Challenge

Use one of these for loops to log to the console all the values in your `cars` array on separate lines?

## Push in and pop out of arrays

Sometimes we actually need to add something else to our array. The easiest way to do this is to use `cars.push(newElement)`. This will add the new item to the end of the list.

Try adding `'renault'` to your cars list using `push`. Put this before your console logging loop so you see your new element logged out.

We can also take the last-added element out of the array using `pop`.

```JS
var last = cars.pop();
```

Here, the `last` variable will be the element that is taken out and the array will no longer have that element.

Have a play around with `push`, `pop` and your console logging loop to see what this does. Also try logging out the `last` element when popping.

That's the array basics out the way, now let's look at objects...

## Creating an object

The easiest way to create a JavaScript object is using curly brackets `{...}`, also known as an object literal. Let's create a car object. Put this in your script file.

```JS
var car = {make: 'VW', model: 'Beetle'};
```

## Accessing and modifying properties

You can access properties using a `.` after the object name. So we can use `car.make` to get the result `'VW'` - try this in the console.

We can use this to set the properties too.

```JS
car.model = 'passat';
```

Do this and then log the car to console to see it with the updated property value.

## Challenge

Arrays can also be properties in objects and objects can be in arrays. Let's create an array of objects.

Start by creating an array of colour names.

Then create a different array of car names.

Then, using a loop, like the one [above](#for%20loop) generate an object that contains a random car name and a random colour. The aim is to get an object that looks like this:

```JS
{
  car: 'ford',
  colour: 'signal orange'
}
```

You can select a random item from an array using this code:

```JS
var randomColour = colours[Math.floor(Math.random() * colours.length)];
```

Once you have created your new object, push it to a `cars[]` array.

After the loop, `console.log()` your `cars[]` array.

### Stretch goals

- Console.log the results of your loop, printing each of the properties with keys and values in a list with a clear separation between each different object.

All done? Time to learn about [Functions](05-functions.md).
