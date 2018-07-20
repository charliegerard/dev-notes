# Quick Sort

Quick sort is a **recursive** sorting algorithm that employs a **divide and conquer** strategy.

The concept of this algorithm is to split a problem into smaller versions of itself.

It sorts a collection by choosing a pivot point, and partitioning the collection around this pivot, putting the smaller elements before it and the bigger elements after it.
It recursively continues to break down the collection before combining them back together to create a sorted list.

Three main operations: partition, swap, and sort.

What we are trying to achieve is to partition the list so that everything to the **left of the pivot is less than the pivot** and everything on the **right is greater than the pivot**.

Example of implementation:

```javascript
function quickSort(list, left, right){
  var pivot, partitionIndex;

  if(left < right){
    pivot = right;
    partitionIndex = partition(list, pivot, left, right);
    // move the right index to the left
    quickSort(list, left, partitionIndex - 1);
    // move the left index to the right;
    quickSort(list, partitionIndex + 1, right);
  }

  return list;
}

function partition(list, pivot, left, right){
  var pivotValue = list[pivot];
  partitionIndex = left;

  for(var i = left; i < right; i++){
    if(list[i] < pivotValue){
      swap(list, i, partitionIndex);
      partitionIndex++;
    }
  }
  swap(list, right, partitionIndex);
  return partitionIndex;
}

function swap(list, i, j){
  var temp = list[j];
  list[j] = list[i];
  list[i] = temp;
}

const list = [3,5,2,7,9,8,1];
const sortedList = quickSort(list, 0, list.length-1);
console.log(sortedList);
```

