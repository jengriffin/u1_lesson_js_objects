# Javascript Objects

![Objects](https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fstatic.skillshare.com%2Fuploads%2FparentClasses%2F17abe69859d068286c56e7bd03294415%2Fb0876504&f=1&nofb=1)

## Lesson Overview

In this lesson, we'll discuss Objects and how they are essential data structures in JavaScript.

## Getting Started

- `fork` and `clone`
- `cd` into the new directory
- Use `touch` and create an `objects.js` file
- Run `code .` to open the directory in VS Code

To run your code, use `node objects.js`...

## Lesson Objectives

_After this lesson, students will be able to:_

1. Explain the difference between arrays and objects
2. Store key-value pairs inside an object
3. Access values by key-name
4. Add Object Properties
5. Change Object Properties
6. Explain why we use an object instead of an array
7. Manipulate objects and arrays declared as `const`
8. List common errors made with objects
9. Use object properties with conditionals

## Explain the difference between arrays and objects

We have seen the following datatypes:

- String
- Number
- Boolean

Arrays are a **data structure**. We use them to organize our data: in the case of arrays, we can organize our data into a **sequential list** data structure.

- We can use arrays to store multiple pieces of data as a sequential list:

```js
const car = ['blue', 4000, 1989]
```

- Each element has a corresponding index (or place), in sequence.

But with the array above, we don't know what the values mean. Does "blue" refer to the color of the vehicle? To the mood of the owner? Is it the model of the vehicle?

- An object is also a **data structure**, but we can use objects to store data with greater specificity.

- In JavaScript, **objects** are what we use to represent **key-value** pairs.

## Store key-value pairs inside an object

Key-value pair syntax:

```js
const car = {
  color: 'blue',
  hp: 4000,
  year: 1989
}
```

- Unlike arrays, objects use _named keys_ rather than ordered indexes. Each piece of data is _bound_ to its key, rather than assigned an index. The data is not _sequential_.

- In Javascript, an object is a way to group many pairs of keys and values together

We can console.log the entire object:

```js
console.log(car)
```

## Access values by key-name

We can access the values stored in key using dot notation:

```js
console.log(car.color)
```

## DIFFERENCES BETWEEN ARRAYS AND OBJECTS

- Arrays are declared using the square brackets `const arr = []`
- Objects are declared using the curly braces `const obj = {}`

Objects contain _key-value pairs_. They are are the **properties** of the object.

A **key** is like an **index** in an array, but it has:
- a name
- it is unique

A key is really a string but we can omit the quotes.

A **value** is what a key _refers to_, and can be *any* datatype.

## Add Object Properties

You can easily add more properties to a previously declared object:

```js
const house = {
  doors: 9
}

console.log(house)
```

> => { doors: 9 }

Add properties to the `house` object by simply adding a key using dot notation and the value using an equals `=`. Our house has no windows. Let's add some in _without_ writing them straight into the object:

```js
house.windows = 30
```

When we do it this way, the `windows` key is added to the object.

```js
console.log(house)
```

> => { doors: 9, windows: 30 }

Add another property `hasGarden`:

```js
house.hasGarden = true
```

## Change Object Properties

Changing the value of an existing key has the same syntax as creating a new key-value pair:

```js
const recipe = {
  isYummy: false
}
```

```js
recipe.isYummy = true
```

## Why We Use An Object Instead of an Array

When designing your programs, it is up to you to **choose** how to model your data. We can represent real-life things with our datatypes, but it's a matter of choosing the appropriate datatypes.

If the thing you want to model is just a list, use an **array**.

If the thing want to model has properties, use an **object**.

Using what we know about datatypes so far, which datatype would we use to model:

1. The name of your cat
2. The age of your cat
3. A list of your cat's favorite things
4. Whether your cat is asleep
5. Your cat

## Manipulate objects and arrays declared as `const`

`const` only prevents you from reassigning a variable; it doesn't prevent you from adding or changing elements of arrays or properties of objects.

You can do this:

```js
const cat = {}

cat.name = 'Gizmo'
```

Cannot do this:

```js
const cat = {}

cat = { name: 'Gizmo' }
```

## List common errors made with objects

### Unique Keys

It just makes sense that keys ought to be unique within an object. Values, however, can be repeated.

An object cannot have more than one key with the same name. If it does, the value will default to the last key with the same name, and the prior properties will be excluded on creation.

```js
const borough = {
  name: 'Brooklyn',
  name: 'The Bronx'
}
```

```js
console.log(borough)

=> { name: "The Bronx" }
```

Conclusion: keys should be unique within an object. Values, however, do not have to be unique.

### Accessing and Naming Keys Using Brackets and Quotes

You can create and access any key with square brackets and quotes.

```js
const goblin = { 
  badGuy: true
}
```

```js
console.log(goblin['badGuy'])

=> true
```

With square brackets and quotes, you can make key names with spaces and special characters, because the key is _coerced_ into a string. _But_, you then have to access the value from here on out with square brackets and quotes.

```js
const strangeObj = {}

strangeObj['a key with spaces'] = 999

console.log(strangeObj)

=> { 'a key with spaces': 999 }
```

You would need also to access that key with the square brackets and quotes:

```js
console.log(strangeObj['a key with spaces'])

=> 999
```

You could not access that key using dot notation. The spaces prevent that from being possible.

Square brackets are nice if you need to programmatically generate a key name:

```js
const obj = {}

for (let i = 0; i < 10; i++) {
  obj['key' + i] = 'some value'
}

console.log(obj)
```

### Keys That Are Numbers

If a key is just a number, that number will be *coerced* into a string, which is fine.

```js
const obj = {
  1: 'one'
}
```

```js
console.log(obj)

=> { '1': 'one' }
```

But, you cannot access, add, or change numbered keys with dot notation.

```js
console.log(obj.1)
```

```js
obj.2 = "hey"

console.log(obj.2)
```

This is another situation where accessing key-values using square brackets and quotes is helpful: `obj['1']`

## Use object properties with conditionals

You can use object properties with conditionals, loops, etc...

```js
const obj = {
  text: 'hi',
  count: 4
}

if (obj.text == 'hi') {
  console.log('ok')
}

for (let i = 0; i < obj.count; i++) {
  console.log(i)
}
```

You can test to see if a property exists on an object:

```js
const saturn = {
  hasRings: true
}

if (saturn.hasRings) {
  console.log('This key exists within the object')
}

if (saturn.isSafe) {
  console.log('This key exists within the object')
} else {
  console.log('This key does not exist within the object')
}
```

This is because accessing a property that doesn't exist on an object gives you `undefined` which is a `falsy` value.

## Lesson Recap

We will use objects in JavaScript every day, and you will have plenty of time to practice creating and using them. There are a lot of resources available on the web for you to dive deeper, but the most detailed and understandable one is probably [MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object).

## Resources

- [JavaScript Reference](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object)
- [Intro to Object-Orientated Javascript](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Introduction_to_Object-Oriented_JavaScript)
- [Objects in Javascript](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Working_with_Objects)
