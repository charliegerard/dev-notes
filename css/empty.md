# CSS selector :empty

If you want to change the style of an element when it is empty, you can use the `:empty` CSS selector.

```html
<div class="box">Hello World</div>
<div class="box"></div>

<style>
  .box{
    width: 50px;
    height: 50px;
    background-color: pink;
  }

  .box:empty{
    background-color: grey;
  }
</style>
```
