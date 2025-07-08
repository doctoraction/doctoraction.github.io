# Modern JS & Node/NPM/etc

## Misc

`npm init -y` creates package.json

`npm install --save chromedriver@107.0.3` install specific version and update package.json

`npm install --save-dev` saves under devDependencies - won't be packaged for deployment

`npm install -g` (installs packages globally to home directory)

Once installed globally you don't need to run npm ...
  eg: `create-react-app some_name` not `npm create-react-app some_name`

`npx something` - executes without installation (!?)

`npm run somethinginpackagejsonscripts`

`npm publish`

`npm update`

`npm list`

`npm audit fix`

`npm show packagename` - shows latest version

`npm view chromedriver versions`

## Types, Objects, Arrays ...

**Objects** are collections of properties (simple values, objects or functions).

`person.name.first`

`person["name"]["first"]`

Using object Constructors

```
function Person(name) {
  this.name = name;
  this.introduceSelf = function () {
    console.log(`Hi! I'm ${this.name}.`);
  };
}

const salva = new Person("Salva");
```

**Arrays** are a special type of object. The typeof operator in JavaScript returns "object" for arrays.
Arrays have extra methods and properties. eg. `cars.length`, `cars.sort()`
Arrays can use numbers to access elements while objects always use names

```
someArray[0]
someObject.someProperty
```

**Object or Array?**
When user assigns values to keys with datatype Array, it transforms into an object
Any array with a string key (rather than a numeric one) loses it's length property.

[Looping over arrays and objects](https://medium.com/chingu/looping-over-arrays-and-objects-in-javascript-57e1188c1ba2)

What creates an array and what a plain object?

### Inheritance

Each object has a private property which holds a link to another object called its prototype, that protoype has a prototype, etc, until that prototype is `null`.

The property of an object that points to its prototype is not called prototype. Its name is not standard: all browsers use `__proto__`, ECMAScript standard is `someObject.[[Prototype]]`.
The standard way to access an object's prototype is `Object.getPrototypeOf(someobject)` and there is a `Object.setPrototypeOf(obj, prototype)`.
When we try to access a property, the engine looks in the objects, then the prototype, then that one's prototype, etc.
So objects inherit all properties of the prototypes chain.

(Note: The `func.prototype` property of functions specifies the [[Prototype]] to be assigned to **all** instances of objects created by the given function when used as a constructor.)


## Classes

Similar to function iobject constructors. Key features of classes:

* Constructor
* Instance methods and instance fields
* Static methods and static fields

```
class MyClass {

  constructor() {
  }
  myField = "foo";
  getMyField() {
    return this.myField;
  }
    
  static myStaticField = "bar";
  static myStaticMethod() {  
  }
  static {
  }
  
  // Fields, methods, static fields, and static methods all have
  // "private" forms
  #myPrivateField = "bar";
}

const myInstance = new MyClass(); // new is mandatory
console.log(myInstance.myField); // 'foo'
myInstance.getMyField();

console.log(MyClass.myStaticField) // static reference - not available on instances
console.log(MyClass.myStaticMethod()) // static reference - not available on instances

class AnotherClass extends MyClass {
}

```

Private fields support Java style encapsulatiom. However, a class method **can** read the private fields of other instances of the same class.

## Functions

## TypeScript

`npm install -g typescript`

`tsc` - tsc on .ts files creates js files.

Without changes TS will ensure number of function args are the same.

In Java, it’s meaningful to think of a one-to-one correspondence between runtime types and their compile-time declarations.
In TypeScript, it’s better to think of a type as a set of values that share something in common. Because **types are just sets**, a particular value can belong to **many sets at the same time**.
Primitive types:

`string`, `number` and `boolean`

`string[]`

`any`

`let davevar: string = 'sausage';`

Parameter and return type annotations:

```
function doStuff(somevalue: string) : string {
  return somevalue + 'somesuffix';
}
```

Object type (? makes that property optional)

`function printName(obj: { first: string; last?: string }) { }`

## Promises
https://masteringjs.io/tutorials/fundamentals/promise

A promise represents an async action. Calling a function that returns a promise is asking something to do an async action, and there are ways to receive the results of that action.

```
const promise = axios.get("http://asdasd");
// register a callback function called when succeeds
promise.then(res => {
  res.data.query.answer;
})
```
When a promise is settled, any handler functions that you registered using .then() are called. The then() function takes 2 parameters: onFulfilled and onRejected. JavaScript calls onFulfilled() if the promise is fulfilled, or onRejected() if the promise is rejected.

```
// a promise that is immediately fulfilled with value 42.
const promise = Promise.resolve(42);

const onFulfilled = () => {};
const onRejected = () => {};

// `onFulfilled` called if the promise is fulfilled, `onRejected` if the promise is rejected.
promise.then(onFulfilled, onRejected);

// promises return values accesible via the then function
promise.then(value => {
  value; // 42
});

// a promise immediately rejected
const promise = Promise.reject(new Error('Oops!'));
// note the parameter position of err
promise.then(null, err => {
  err.message; // 'Oops!'
});
```
You can instantiate a promise using new Promise().

The promise constructor takes 1 function parameter: called executor. The executor function takes two parameters: callback functions resolve() and reject().
As someone creating a promise, you write the executor function, and the JavaScript runtime is responsible for passing you resolve() and reject().
As the writer of the executor function you are providing the value to the resolve function that the caller has specified.
```
const promise = new Promise(function executor(resolve, reject) {
  // Fulfill the promise with value '42' after 100 ms.
  setTimeout(() => resolve(42), 100);
});

promise.then(value => {
  value; // 42
});
```

## Async/Await
`async` makes a function return a Promise
`await` makes a function wait for a Promise

The keyword `async` before a function declaration makes the function return a promise

The keyword `await` keyword makes the function pause the execution and wait for a resolved promise before it continues.
The `await` keyword can only be used inside an `async` function.

## Jest

    expect - returns an expectation object
    toBe - exact match "IS the obj"
    toEqual - value is equal
    expect(a + b).not.toBe(0);
    toBeTruthy matches anything that an if statement treats as true
    toBeFalsy

    beforeEach(() => {
      initializeCityDatabase();
    });

    afterEach(() => {
      clearCityDatabase();
    });

    beforeAll(() => {
      return initializeCityDatabase();
    });

    afterAll(() => {
      return clearCityDatabase();
    });

    test.only

## testing-library react

    built on top of DomTestingLibravy

    use reander
    then do normal expect stuiff on hte resukts?

