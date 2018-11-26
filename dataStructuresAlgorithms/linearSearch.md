# Linear search

Most basic search algorithm.
It sequentially moves through your collection / array looking for a matching value.

The worst case scenario for a linear search is
that it needs to loop through the entire collection to find a match, either because the item we are looking for is the last one or because it doesn't exist.

![Linear search gif](https://www.tutorialspoint.com/data_structures_algorithms/images/linear_search.gif)


Example in JavaScript:

```javascript
const numbers = [8,4,5,3,1,9];

const linearSearch = numberToFind => {
  for(let i = 0; i <= numbers.length; i++){
    if(numbers[i] === numberToFind){
      return i;
    }
  }
}

linearSearch(9); // returns the index 5.
```
