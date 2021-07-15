## Design a function `mix()` to mixin Classes

### Tags

Class/reduce()/

### Q

```javascript
class Vehicle {}
let FooMixin = (Superclass) =>
  class extends Superclass {
    foo() {
      console.log("foo");
    }
  };
let BarMixin = (Superclass) =>
  class extends Superclass {
    bar() {
      console.log("bar");
    }
  };
let BazMixin = (Superclass) =>
  class extends Superclass {
    baz() {
      console.log("baz");
    }
  };

// function mix there

class Bus extends mix(Vehicle, FooMixin, BarMixin, BazMixin) {}
let b = new Bus();
b.foo(); // foo
b.bar(); // bar
b.baz(); // baz
```

### Answer

```JavaScript
function mix(BaseClass, ...Mixins) {
 return Mixins.reduce(
   (accumulator, current) => current(accumulator), BaseClass);
}
```

### Knowledge
