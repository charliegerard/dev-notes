# Mixins in React.js

When multiple components have the same functionalities and you want to avoid duplications, you can write mixins.
React has some built-in mixins but you can create your own.

For example, if we wanted to write a HelloWorld mixin to help us share a function that would return 'Hello World', we would do the following:

Create a new file called HelloWorldMixin.js and write:

```
export default {
  sayHelloWorld: {
    return 'Hello World';
  }
}
```

Next, in the component file where you need to use this function, import your mixin at the top by writing:

```
import HelloWorldMixin from './HelloWorldMixin'
```

Then, your component should look like:

```
  export default React.createClass({
    mixins: [HelloWorldMixin],
    displayName: 'exampleComponent',

    render(){
      return(
        <div>
          <p>{this.sayHelloWorld()}</p>
        </div>
      )
    }
  })
```
