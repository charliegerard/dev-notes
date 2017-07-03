# Basic CS terms
---

* *Class*: a blueprint for how a data structure should function.

* *Constructor*: instructs the class to set up the initial state of an object.

* *Object*: instance of a class that stores the state of a class.

* *Method*: set of instructions that can be called on an object.

* *Parameter*: values that can be specified when creating an object or calling a method.

* *Return value*: specifies the data type that a method will return after it runs.

* *Inheritance*: allows one class to use functionality defined in another class.


## Data structures
---

* *ArrayList*: stores a list of data of a specified type.

```java
//Java
ArrayList<Integer> grades = new ArrayList<Integer>();
//To add values to an array, you can use the add() function;
grades.add(10);
```

* *HashMap*: a hashmap is like a dictionary containing sets of keys and a value for each key.

```java
//Java
HashMap<String, Integer> friends = new HashMap<String, Integer>();
//To add values to a hashmap, you can use the put() function;
friends.put("Boo", 2);
```

## Variable types
---

* *char*: A single character. Should be initiated using single quotes. **char is a primitive type.**

```java
char letter = 'a';
```

* *string*: Object containing multiple characters. Should be initiated with double quotes. **String is not a primitive type, it's a reference type.**

```java
String text = "Hello world";
```

If trying to access a character in a string, the following triggers an error:

```java
String dnaStrand;
int item = 0;
dnaStrand.charAt(item).toString();
//error: char cannot be dereferenced
```
As char is a primitive and not an object, it cannot be dereferenced. To access a character in a string, it should be done that way:

```java
String dnaStrand;
int item = 0;
Character.toString(dnaStrand.charAt(item));
```

**The 8 variable types are:**

* boolean
* char
* int
* float
* byte
* short
* long
* double
