# Insertion sort

Sorting algorithm that builds a sorted array one element at a time.

![Insertion sort algorithm](https://ds055uzetaobb.cloudfront.net/image_optimizer/a30e63f265b319f6c9658e7b1a46da9ef8ba7e34.gif
)

* Start from the left.
* For each next element, compare it to each element to the left of it, move right to left until it "fits" in the sorted portion of the array.
* Since we insert the element in the sorted portion of the array, the result will be sorted.

If we take an array made of 10 elements.

The best case scenario will have 9 comparisons and the worst case scenario will produce 45 comparisons.

```javascript
const list = [3,2,6,9,4,1,0,45,12,36,78]

const insertionSort = list => {
  for(var i = 1; i < list.length; i++){
    var temp = list[i];
    for(var j = i-1; j > -1 && list[j] > temp; j--){
      list[j+1] = list[j]
      list[j] = temp
    }
  }
  return list
}

console.log(insertionSort(list))
```
