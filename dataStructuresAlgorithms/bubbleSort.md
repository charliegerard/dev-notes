# Bubble sort

Naive algorithm that iterates through an array and checks if each current item is in order or swaps it. After doing it enough times, we will end up with a sorted array.

![Bubble sort](https://upload.wikimedia.org/wikipedia/commons/0/06/Bubble-sort.gif)

```javascript
let list = [4,6,1,0,3,7,2]

const bubbleSort = list => {
  let swapped = false;

  do{
    swapped = false;
    for(var i = 0; i < list.length; i++){
      if(list[i+1] < list[i]){
        var temp = list[i]
        list[i] = list[i+1]
        list[i+1] = temp

        swapped = true;
      }
    }
  } while(swapped)

  return list;
}
console.log(bubbleSort(list))
```

Or, with recursion:

```javascript
const list = [3,6,1,8,2,0,4]

const bubbleSort = (list, pointer = list.length - 1) => {
  if(pointer === 0){
    return list
  }
  for(var i = 0; i < pointer; i++){
    if(list[i] > list[i+1]){
      var temp = list[i+1]
      list[i+1] = list[i]
      list[i] = temp
    }
  }
  return bubbleSort(list, pointer - 1)
}

console.log(bubbleSort(list))
```

