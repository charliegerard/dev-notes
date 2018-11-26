# Binary search

Considering a sorted array, binary search repeatedly chooses a number in the middle of the remaining possible numbers, and then determines if the desired number would like to the left or right of this chosen number (or exactly the chosen number).
In each iteration, the amount of remaining number is halved, making binary search very efficient.


![binary tree gif](https://ds055uzetaobb.cloudfront.net/image_optimizer/717403b1368376cb6f915e6b4beeb3a7ad54105e.gif)

Example code in JavaScript:

```javascript
const numbers = [1,2,3,4,5,6,7]; // array already sorted.

const binarySearch = numberToFind => {
  let low = 0;
  let high = numbers.length;

  while(low <= high){
    let middle = Math.floor((low + high) / 2);

    if(numberToFind === numbers[middle]){
      return middle;
    } else if(numberToFind < numbers[middle]){
      high = middle - 1;
    } else if(numberToFind > numbers[middle]){
      low = middle + 1;
    }
  }
}

console.log(binarySearch(6)); // 5
```
