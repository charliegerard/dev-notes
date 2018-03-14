# Composition and inheritance

Composition and inheritance are two design patterns.

**Inheritance** is when you organise your classes based on what they *are*.

**Composition** is when you organise your classes based on what they *do*.

---

Example: We need a dog and a cat:

```
Dog
  .bark()

Cat
  .meow()
```

Then, we realise both of them need to eat.

```
Dog
  .bark()
  .eat()

Cat
  .meow()
  .eat()
```

This creates duplication that we can extract in an Animal class.

```
Animal
  .eat()

  Dog
    .bark()

  Cat
    .meow()
```

After animals, we need a cleaning robot and a murder robot:

```
CleaningRobot
  .drive()
  .clean()

MurderRobot
  .drive()
  .kill()
```

Once again, there is duplication with *drive*, so we can extract that in a Robot class.

```
Robot
  .drive()

  CleaningRobot
    .clean()

  MurderRobot
    .kill()
```

If your application stayed like that, it would work fine. However, now we need a **MurderRobotDog** that can *drive*, *bark*, *kill* but can't *eat*.

We could create another class before Robot that would have our *bark* functionality and have MurderRobotDog inherit from MurderRobot like below but that would mean our objects would have a lot of functionality they don't need.

```
Game
  .bark()

  Robot
    .drive()

    CleaningRobot
      .clean()

    MurderRobot
      .kill()

      MurderRobotDog
```

This is where **composition** is a better approach than **inheritance**.

Composition helps you organise your code base on whay your objects *do*.

With composition, our app would look something more like this:

```javascript
const barker = (state) => ({
  bark: () => console.log('Woof, I am ' + state.name)
})
const driver = (state) => ({
  drive: () => ({})
})
```

```javascript
const murderRobotDog = (name)  => {
  let state = {
    name,
    speed: 100,
    position: 0
  }
  return Object.assign(
        {},
        barker(state),
        driver(state),
        killer(state)
    )
}
const bruno =  murderRobotDog('bruno')
bruno.bark() // "Woof, I am Bruno"
```

In the case above, we create a barker, driver and killer that we then merge into a new object and return it as part of our murderRobotDog object.

