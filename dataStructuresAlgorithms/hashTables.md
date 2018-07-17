# Hash tables

**Hash tables are data structures to store data.**

They are made of 2 parts:

* An array where the data is stored.
* A hash function: function that maps to certain location in the array.
Mapping between element and where it lives in the array.
The hash function is used to add, remove and find an element from the array.

**A hash function is made of sets of pairs made of key, value.**

Each location in the array is called a **hash bucket**.

A collision occurs when the hash functions tried to insert an item at the same index of another item in the array.

**Clustering**: Data in a hash table is not evenly distributed.

Example:

A dictionary or a phone book.

Every single word has to map with one of the 26 letters of the alphabet.

**26 hash buckets.**

If we wanted to find the name of a person starting with "Z", we could take that as input, pass it into a hash function and get the index in the array.
It is easier to find a single element in a huge data set once we know the key where it lives.

All words starting with the letter A will live at the same hash bucket.

## Time complexity

Constant time because it always takes the same amount of time to find an element by index.

When using an array, we might have to go through all the elements to find the one we are looking for whereas hash table, we get the exact index of where the element should live. O(1).

*Array or linked list is maybe a better data structure to find element in big data set if there is a lot of clustering.*

---

More info: https://dev.to/vaidehijoshi/hash-tables--basecs-video-series-36gh
