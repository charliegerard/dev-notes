# Quick Sort

Quick sort is a **recursive** sorting algorithm that employs a **divide and conquer** strategy.

The concept of this algorithm is to split a problem into smaller versions of itself.

It sorts a collection by choosing a pivot point, and partitioning the collection around this pivot, putting the smaller elements before it and the bigger elements after it.
It recursively continues to break down the collection before combining them back together to create a sorted list.

Three main operations: partition, swap, and sort.

![quick sort](https://upload.wikimedia.org/wikipedia/commons/9/9c/Quicksort-example.gif)

What we are trying to achieve is to partition the list so that everything to the **left of the pivot is less than the pivot** and everything on the **right is greater than the pivot**.

### Example of implementation:

#### Naive solution

```javascript
const list = [4,7,1,2,0,3,8]

const quickSort = list => {
  if(list.length < 2){
    return list
  }
  let pivotIndex = list.length - 1;
  let pivot = list[pivotIndex];
  let left = [];
  let right = [];

  for(var i = 0; i < pivotIndex; i++){
    list[i] < pivot ? left.push(list[i]) : right.push(list[i]);
  }

  let result = [...quickSort(left), pivot, ...quickSort(right)];
  return result;
}

console.log(quickSort(list));
```

This solution is naive because we are creating a left and right array that we are then merging which increases the space complexity.

Instead, we could do **in-place sorting**.

#### More complex solution:

```javascript
const list = [5,8,1,4,2,6,7,3,9]

const quickSort = (list, left, right) => {
  if(left < right){
    let pivotIndex = partition(list, left, right);
    quickSort(list, left, pivotIndex - 1);
    quickSort(list, pivotIndex + 1, right);
  }
  return list;
}

const partition = (list, left, right) => {
  let pivot = right;
  let pivotValue = list[pivot];

  while(left < right){
    while(list[left] < pivotValue){
      left++
    }
    while(list[right] > pivotValue){
      right--
    }

    swap(list, left, right);
  }
  return right;
}

const swap = (list, left, right) => {
  let temp = list[left];
  list[left] = list[right];
  list[right] = temp;
}

console.log(quickSort(list, 0, list.length - 1))
```

