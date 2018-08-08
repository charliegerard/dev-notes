# Merge sort

The concept of the merge sort algorithm relies on the fact that it's easier to sort 2 sorted arrays rather than one unsorted one.

We start with one array that we split in the middle into two smaller arrays and repeat this until we reach single-item arrays.

```
[9, 5, 1, 8, 3]

[9, 5, 1] | [8, 3]

[9, 5] | [1] [8, 3]

[9] | [5] [1] | [8] [3]

[5, 9] | [1, 8] | [3]

[1, 5, 8, 9] | [3]

[1, 3, 5, 8, 9]
```

In code, using JavaScript, it could look something like this:

```javascript
const mergeSort = array => {
  if(array.length === 1){
    return array;
  }

  const middle = Math.floor(array.length / 2);
  const left = array.slice(0, middle);
  const right = array.slice(middle);

  return merge(mergeSort(left), mergeSort(right));
}

const merge = (left, right) => {
  let result = [];
  let leftIndex = 0;
  let rightIndex = 0;

  while(leftIndex < left.length && rightIndex < right.length){
    if(left[leftIndex] < right[rightIndex]){
      result.push(left[leftIndex]);
      leftIndex++;
    } else {
      result.push(right[rightIndex]);
      rightIndex++;
    }
  }

  return result.concat(left.slice(leftIndex)).concat(right.slice(rightIndex))
}

const list = [9, 5, 1, 8, 3];
console.log(mergeSort(list));
// [1, 3, 5, 8, 9];
```
