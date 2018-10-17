# Constructor Exercises

1.
  * Create a Human constructor function that takes in a name and age.
  * Add a prototype function ageOneYear that ages the humans age.
  * Add a prototype function eating, that logs "mmm, mmm, mmm, I'm love'n it".
  * Create an instance of the Human class.
    * console log your humans age
    * call ageOneYear on your human
    * console log their age again.
    * call eating on your human.

    function Human(name, age) {
      this.name = name;
      this.age = age;
    }
    Human.prototype.ageOneYear = function () {
      this.age++;
      return `A year has passed, I am now ${this.age}`
    };

    Human.prototype.eating = function () {
      return `Mmm, mmm, mmm, I'm lovin it`
    };

    let michael = new Human("Michael", 38);
    console.log(michael.age);
    console.log(michael.ageOneYear());
    console.log(michael.age);
    console.log(michael.eating());

2.
Write a constructor Vector that represents a vector in two-dimensional space.
It takes two number arguments: `x` and `y` parameters, which it should be saved to properties of the same name.

Give the Vector prototype two methods, `plus` and `minus`, that take another vector as an argument and
returns a new vector that has the sum or difference of the two vectors’ (the one in `this` and the parameter) x and y values.

Add a method `getLength` to the prototype that computes the length of the vector ;
that is, the distance of the point (x, y) from the origin (0, 0).(a^2 + b^2 = c^2)

```js
var v1 = new Vector(1, 2)
var v2 = new Vector(2, 3)
console.log(v1.plus(v2));
// => Vector {x: 3, y: 5}
console.log(v1.minus(v2));
// => Vector {x: -1, y: -1}

var v3 = new Vector(3, 4)
console.log(v3.getLength());
// => 5
```

function Vector (x, y) {
  this.x = x;
  this.y = y;
}

Vector.prototype.plus = function (el) {
  return new Vector (this.x + el.x, this.y + el.y)
};

Vector.prototype.minus = function (el){
return new Vector (this.x - el.x, this.y - el.y)
};

Vector.prototype.getLength = function () {
  return Math.sqrt(Math.pow(this.x, 2) + Math.pow(this.y, 2));
};

let v1 = new Vector (1, 2);
let v2 = new Vector (2, 3);
let v3 = new Vector (3, 4);

console.log(v1.plus(v2));
console.log(v1.minus(v2));
console.log(v3.getLength());
