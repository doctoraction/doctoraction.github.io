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
`tsc`
 
tsc on .ts files creates js files. 
without changes TS will ensure number of function args are the same

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

