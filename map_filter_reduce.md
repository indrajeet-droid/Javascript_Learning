```javascript
// map = Transform items
const numbers = [1, 2, 3, 4, 5];

let doubleNumbers = numbers.map((n) => {
  return n * 2;
});

console.log(doubleNumbers); // [2, 4, 6, 8, 10]

// filter = Select items
let evenNumbers = numbers.filter((n) => {
  return n % 2 === 0;
});

console.log(evenNumbers); // [2, 4]

// reduce = Combine items into one value
let total = numbers.reduce((accumulator, currentValue) => {
  return accumulator + currentValue;
}, 0);

console.log(total); // 15
```javascript
