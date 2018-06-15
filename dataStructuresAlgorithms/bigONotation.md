# Big O Notation

Big-O notation is the relative representation of the complexity of an algorithm. It shows how **an algorithm scales**.

Used to compare algorithmic performance.

How does the performance of an algorithm scale as a function of the input size?

If we take basic arithmetic operations as an example. In school, we learnt:

```
* addition

* substraction

* multiplication

* division
```

A method for solving each of these operation is called an **algorithm**.

* Addition is the simplest.
Take 2 numbers 123456 and 789012. To add them together, we have to add 6 digits (and possibly carry a 7th). If we add two 100 digitt numbers together, we have to do 100 additions. If we add two 10,000 digit numbers, we have to do 10,000 additions.

The **complexity** (being the number of operations) is directly proportional to the number of digits n in the larger number. We cann this **O(n)** or **linear complexity**.

* Substraction is similar.


* Multiplication is different. To multiply  two 6 digit numbers, we must do 36 multiplications.

If we have two 100 digit numbers, we need to do 10,000 multiplications and 200 additions.

As the algorithm scales with *n-squared*, this is **O(n2)** or **quadratic complexity**.

**We only care about the most signification portion of complexity**.

In the example above, the number of operations is actually O(n2) + 2n *(for the number of additions)*.


## Example: Telephone book
---

If we wanted to find a name like "John Doe" in a phone book of 1,000,000 names, we would do a **binary search**. We would start by opening the book in the middle and see if our "John Doe" is in the 1st half or the second half. Logically, it would probably be in the 1st half, so we repeat the same operation in the 1st half until we find our name.

By using a binary search, it would take us at most 20 searches.

```
For 7 names, it takes at most 3.
For 15, it takes 4.
...
For 1,000,000 it takes 20.
```

This is **O(log)** or **logarithmic complexity**. The logarithm could be in different base, it does not matter.

O(2n2), O(100n2) are still both O(n2).

Big O can be used to determine 3 cases with an algorithm:

```
Best case: O(1) or constant complexity.

Expected case: O(log n)

Worst case: O(log n).
```

## Travelling salesman.
---

If we have 3 towns A, B and C with roads betwen all pairs, we could have:

```
A - B - C
A - C - B
B - C - A
B - A - C
C - A - B
C - B - A
```

But actually there are less pairs than that because some roads are the same, just in reverse.

There are actually 3 possibilities.

If we have 4 towns, this number of possibilities goes to 12, with 5 it's 60, etc...

This is called a **factorial**.

```
5 towns = 5 x 4 x 3 x 2 x 1 = 120
```

The Big-O of the travelling salemans problem is O(n!) or **factorial or combinatorial complexity**.

### Recap

**O(n2)**: **Quadratic complexity**.

```
1 item: 1s.
10 items: 100s.
100 items: 10000s.
```

The number of items increases by 10 so n=10 and so O(n^2) gives us the scaling factor n^2 which is 10^2.


**O(n)**: **Linear complexity**.

```
1 item: 1s.
10 items: 10s.
100 items: 100s.
```

The time to execute the function is proportionate to input size *n*.

**O(1)**: **Constant complexity**

```
1 item: 1s.
10 items: 1s.
100 items: 1s.
```

**O(log n)**: **Logarithmic complexity**

```
1 item: 1s.
10 items: 2s.
100 items: 3s.
```

The number of computations is only increased by a log of the input value.
A good example is binary searches.

Another example of **logarithmic time complexity**:

```javascript
for(var i = 0; i < n; i*=2){
  console.log(i);
}
```

## Example programs
---

```python
def add(numberOne, numberTwo):
  return numberOne + numberTwo
```

The Big-O notation for this function would be `O(1)` because no matter how big our input is, it always takes the same amount of time to compute things.


```python
def item_in_list(item_needed, list):
  for item in list:
    if item_needed == item:
      return True
  return False
```

The Big-O notation for this function is `O(n)` because the time it would take to run this function would depend on the size of the input (array of 1 item, 100 items, 1000000 items, etc...)

Of course, we could think about the fact that the item we are looking for could be the 1st in the array but **Big-O is about the approximate worst case performance of doing something**.


```python
def combine_everything(two_dimensional_array):
  result = []
  for item in two_dimensional_array:
    for inner_item in item:
      result.append(inner_item)
  return result
```

This algorithm is considered `O(n^2)` because for `n` item in the list, we have to do `n` more operations, so `n*n` which is `n^2`.

## Calculating Big-O
---

```python
def increment(list):
  total = 0
  for element in list:
    total += 1
  return total
```

Let's look at our calculations here:

* We're setting a variable `total` to 0.
* We loop through a list.
* We add 1 to `total` every time.

So, in Big-O, our steps look like this:

```
* O(1)
* O(n)
* O(1)

O(1) + O(n) * O(1) = O(n)
```


Sources:
https://justin.abrah.ms/computer-science/big-o-notation-explained.html

https://medium.freecodecamp.org/my-first-foray-into-technology-c5b6e83fe8f1




