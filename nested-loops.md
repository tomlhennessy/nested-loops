# Nested Loops

## Pairs Maker
Returns a 2D array where the subarrays represent unique pairs of elements from the input array.

```javascript
let pairsMaker = function(arr) {
    // initialise empty array to store pairs
    let pairs = [];

    // outer loop : iterate over each element of the array
    for (let i = 0; i  < arr.length; i++) {
        // inner loop: iterate over elements succeeding the current element from outer loop
        for (let j = i + 1; j < arr.length; j++) {
            // create a pair of elements
            let pair = [ arr[i], arr[j] ];
            // push the pair into the pairs array
            pairs.push(pair);
        }
    }
    return pairs;
}

console.log(pairsMaker(['a', 'b', 'c', 'd'])); // =>
// [ [ 'a', 'b' ],
//   [ 'a', 'c' ],
//   [ 'a', 'd' ],
//   [ 'b', 'c' ],
//   [ 'b', 'd' ],
//   [ 'c', 'd' ] ]
```

## Two Sum
Returns a boolean indicating if two distinct numbers of the array add up to the target value.

```javascript
let twoSum = function(arr, target) {
    // outer loop: iterate over each element of the array
    for (let i = 0; i < arr.length; i++) {
        // store current element from the array in 'num1'
        let num1 = arr[i];

        // inner loop: iterate over elements succeeding the current element from the outer loop
        for (let j = i + 1; j < arr.length; j++) {
            // store the next element from array in 'num2'
            let num2 = arr[j];

            // check if sum of 'num1 and 'num2' equals target number
            if (num1 + num2 === target) {
                return true;
            }
        }
    }
    // if no pair of numbers adds up to the target, return false
    return false
}

console.log(twoSum([1, 7, 3, 0, 2], 5)); // true
console.log(twoSum([1, 7, 3, 0, 2], 6)); // false
```

## Pair Product
Returns a boolean indicating whether or not a pair of distinct elements in the array result in the product when multiplied together.

```javascript
let pairProduct = function(numbers, product) {
    // outer loop: iterate over each element of the array
    for (let i = 0; i < numbers.length; i++) {
        // inner loop: iterate over elements succeeding the current element from outer loop
        for (let j = i + 1; j < numbers.length; j++) {
            // check if product of numbers[i] and numbers[j] meets target
            if (numbers[i] * numbers[j] === product) {
                // if the product equals target, return true
                return true;
            }
        }
    }
    // if no pair of numbers has the specified product, return false
    return false;
}

console.log(pairProduct([4, 2, 5, 8], 16))    // true
console.log(pairProduct([4, 2, 5, 7], 16))    // false
```

## Strange Sums
Iterates through every pair of elements in the array and checks if their sum equals zero. If such a pair is found, it increments the 'count' variable. It returns the total count of pairs whose sum is zero.

```javascript
let strangeSums = function(numbers) {
    // intialise variable count to keep track of pairs w/ sum of 0
    let count = 0;

    // outer loop: iterate over each element
    for (let i = 0; i < numbers.length; i++) {
        // inner loop: iterate over elements succeeding the current element from outer loop
        for (let j = i + 1; j < numbers.length; j++) {
            if (numbers[i] + numbers[j] === 0) {
                // if sum equals zero, increment the 'count' variable
                count++;
            }
        }
    }
    // return total count of pairs whose sum is zero
    return count;
}
