# Passing Functions as Props

## Lists and Keys
[All notes were taken from here](https://reactjs.org/docs/lists-and-keys.html)
- What does .map() return? <br>
It returns an array of equal length to the original.
- If I want to loop through an array and display each value in JSX, how do I do that in React?<br>
```ES6
const numbers = [1, 2, 3, 4, 5];
const listItems = numbers.map((numbers) =>
  <li>{numbers}</li>
);

ReactDOM.render(
  <ul>{listItems}</ul>,
  document.getElementById('root')
);
```
- Each list item needs a unique **key**.
- What is the purpose of a key?<br>
Keys help React identify items that have changed.

## Spread Operator
[All notes were taken from here](https://medium.com/coding-at-dawn/how-to-use-the-spread-operator-in-javascript-b9e4a8b06fab)
- What is the spread operator?<br>
  `...` is the notation of the **spread operator** which "spreads" an array into seperate arguments.
- List 4 things that the spread operator can do.<br>
  1. Copy an array
  2. Combine an array
  3. Use Math functions
  4. Using an array as arguments
- Give an example of using the spread operator to combine two arrays.<br>

```ES6
[...["ððððĪŠð"]] // Array [ "ððððĪŠð" ]
[..."ððððððĨ°ððĪĐ!"] // Array(9) [ "ð", "ð", "ð", "ð", "ð", "ðĨ°", "ð", "ðĪĐ", "!" ]

const hello = {hello: "ððððĪŠð"}
const world = {world: "ððððððĨ°ððĪĐ!"}

const helloWorld = {...hello,...world}
console.log(helloWorld) // Object { hello: "ððððĪŠð", world: "ððððððĨ°ððĪĐ!" }
```

- Give an example of using the spread operator to add a new item to an array.<br>

```ES6
const myArray = [`ðĪŠ`,`ðŧ`,`ð`]
const yourArray = [`ð`,`ðĪ`,`ðĪĐ`]
const ourArray = [...myArray,...yourArray]
console.log(...ourArray) // ðĪŠ ðŧ ð ð ðĪ ðĪĐ
```

```ES6
const fewFruit = ['ð','ð','ð']
const fewMoreFruit = ['ð', 'ð', ...fewFruit]
console.log(fewMoreFruit) //  Array(5) [ "ð", "ð", "ð", "ð", "ð" ]
```

- Give an example of using the spread operator to combine two objects into one.<br>

```ES6
const objectOne = {hello: "ðĪŠ"}
const objectTwo = {world: "ðŧ"}
const objectThree = {...objectOne, ...objectTwo, laugh: "ð"}
console.log(objectThree) // Object { hello: "ðĪŠ", world: "ðŧ", laugh: "ð" }
const objectFour = {...objectOne, ...objectTwo, laugh: () => {console.log("ð".repeat(5))}}
objectFour.laugh() // ððððð
```


## Passing Functions between Components

[All notes were taken from here](https://www.youtube.com/watch?v=c05OL7XbwXU)
- In the video, what is the first step that the developer does to pass functions between components?<br>
He creates his function in the same location as the state he is looking to change.
- In your own words, what does the increment function do?<br>
The function iterates through the array of people objects and finds the object with the name propery that matches the name that was passed in as an argument. It then increments the count property of that object by one and then returns the object. Finally the function will update the state of the object by using .setState.
- How can you pass a method from a parent component into a child component?<br>
Pass it in similar to a prop. Example from the video:
```ES6
increment={this.increment}
```
- How does the child component invoke a method that was passed to it from a parent component?<br>
Example from the video:
```ES6
this.props.increment(this.props.name)
```
invokes it and passes in the name of the object whose count is going to be incremented.

[Back to HOME](../README.md)