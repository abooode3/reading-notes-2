# React Docs - lists and keys

- What does .map() return? 
return new array with the same length of the original array with diffrent in values

- If I want to loop through an array and display each value in JSX, how do I do that in React? 
i understand we use list with array element  and render it to the DOM!

- Each list item needs a unique ? 
key.

- What is the purpose of a key?
A “key” is a special string attribute you need to include when creating lists of elements

--------------------------------------------------

- What is the spread operator?
>  useful and quick syntax for adding items to arrays, combining arrays or objects, and spreading an array out into a function’s arguments.

- List 4 things that the spread operator can do.?
Copying an array
Concatenating or combining arrays
Using Math functions
Using an array as arguments

- Give an example of using the spread operator to combine two arrays?
const fruits = ['🍏','🍊','🍌','🍉','🍍']
const moreFruits = [...fruits];
console.log(moreFruits) // Array(5) [ "🍏", "🍊", "🍌", "🍉", "🍍" ]
fruits[0] = '🍑'
console.log(...[...fruits,'...',...moreFruits]) //  🍑 🍊 🍌 🍉 🍍 ... 🍏 🍊 🍌 🍉 🍍

- Give an example of using the spread operator to add a new item to an array?
const fewFruit = ['🍏','🍊','🍌']
const fewMoreFruit = ['🍉', '🍍', ...fewFruit]
console.log(fewMoreFruit) //  Array(5) [ "🍉", "🍍", "🍏", "🍊", "🍌" ]

- Give an example of using the spread operator to combine two objects into one?

const objectOne = {hello: "🤪"}
const objectTwo = {world: "🐻"}
const objectThree = {...objectOne, ...objectTwo, laugh: "😂"}
console.log(objectThree) // Object { hello: "🤪", world: "🐻", laugh: "😂" }
const objectFour = {...objectOne, ...objectTwo, laugh: () => {console.log("😂".repeat(5))}}
objectFour.laugh() // 😂😂😂😂😂

-----------------------------------------------------------

# How to Pass Functions Between Components?

- In the video, what is the first step that the developer does to pass functions between components?  
create function inside parent, update the stare,  and call it from child

- In your own words, what does the increment function do? when click on button inside object it should change (increment) state from parent  

- How can you pass a method from a parent component into a child component?  
through props

- How does the child component invoke a method that was passed to it from a parent component? this.function -> this.incremen