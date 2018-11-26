# Binary search

Considering a sorted array, binary search repeatedly chooses a number in the middle of the remaining possible numbers, and then determines if the desired number would like to the left or right of this chosen number (or exactly the chosen number).
In each iteration, the amount of remaining number is halved, making binary search very efficient.


![binary tree gif](https://ds055uzetaobb.cloudfront.net/image_optimizer/717403b1368376cb6f915e6b4beeb3a7ad54105e.gif)

Example code in JavaScript:

```javascript
const binarySearch = (numbers, numberToFind, min, max) => {
  while(min <= max){
    let middle = Math.floor((min + max) / 2);
    if(numberToFind > numbers[middle]){
      return binarySearch(numbers, numberToFind, middle + 1, max);
    } else if(numberToFind < numbers[middle]){
      return binarySearch(numbers, numberToFind, min, middle - 1);
    } else {
      return middle;
    }
  }
}

console.log(binarySearch(numbers, 6, 0, numbers.length - 1)); // 5
```
