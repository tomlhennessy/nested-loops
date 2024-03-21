# Nested Loops
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
