# Void

When declaring functions in Java, the keyword `void` is used when we want to indicate that the **function should not return any value** after it executes all the logic in the method.

If we want the method to return a value after it finishes running, we can specify a *return type*.

Example:

```java
class Car{
  int years;
  public Car(int numberYears){
    years = numberYears;
  }

  public void drive(int distance){
    System.out.println("Number of miles: " + distance);
  }

  public int numberOfTires(){
    return 4;
  }

  public void main(){
    System.out.println("Hello");
  }
}
```
