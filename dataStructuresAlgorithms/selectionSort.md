# Selection sort

A selection algorithm will divide its input between a sorted and
unsorted section.

It will swap the smallest element it finds in each iteration, and add it to the sorted section of elements.

![selection sort](https://codepumpkin.com/wp-content/uploads/2017/10/selectionSort.gif)

```javascript
const list = [3,2,6,9,4,1,0,45,12,36,78]

const selectionSort = list => {
  var min_index;
  for(var i = 0; i < list.length; i++){
    min_index = i;
    for(var j = i+1; j < list.length; j++ ){
      if(list[j] < list[min_index]){
        min_index = j
      }
    }
    var temp = list[i]
    list[i] = list[min_index]
    list[min_index] = temp
  }
  return list
}

console.log(selectionSort(list))
```
