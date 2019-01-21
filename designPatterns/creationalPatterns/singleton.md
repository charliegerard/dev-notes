# Singleton

This pattern ensures that **only one instance of the class will exist, and provide a global point of access to it**.

It helps in situations where you need to have a one-and-only class, where **system-wide actions need to be performed from a central place**. For example, when you want to create logs, you may want a single logging class that creates a single file.

Another case is when you need to represent something unique such as a particular person, monument, etc... for example.

However, other design patterns such as the Factory pattern and Dependency injection have made Singleton obsolete.

#### ES5:

```javascript
var store = (function(){
  var data = [];
  var instance;

  function init(){
    function add(item){
      data.push(item)
    }

    function get(id){
      return data.find(item => {
        return item.id === id;
      })
    }

    return{
      addData: data,
      getData: get
    }
  }

  return {
    getInstance: function(){
      if(!instance){
        instance = init()
      }
      return instance;
    }
  }
})();

var storeA = store.getInstance();
var storeB = store.getInstance();

console.log(storeA === storeB);
```

#### ES6:

```javascript
class UserStore{
  static instance;

  constructor(){
    this.data = [];
    if(instance){
      return instance;
    }

    this.instance = this;
  }
}

const instance = new UserStore();
const otherInstance = new UserStore();
console.log(instance === otherInstance) // true

export default instance;
```

Singletons can be a sign we need to re-evaluate our design. They can be an indication that modules in our system are tightly coupled or that logic is overly spread across multiple parts of the codebase.
