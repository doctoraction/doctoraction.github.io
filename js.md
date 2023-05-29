# Modern JS

## Misc

`npm install -g` (installs packages globally to home directory)

`npm install --savedev` (something v similar to --save)

`npx something` - executes without installation (!?)

Once you've installed a package globally you don't need to run npm ...
  eg: `create-react-app some_name` not `npm create-react-app some_name`

## Functions

## Types, Objects, Arrays ...

Objects are collections of properties (simple values, objects or functions).

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

### Inheritance

Each object has a private property which holds a link to another object called its prototype, that protoype has a prototype, etc, until that prototype is `null`.

The property of an object that points to its prototype is not called prototype. Its name is not standard: all browsers use `__proto__`, ECMAScript standard is `someObject.[[Prototype]]`.
The standard way to access an object's prototype is `Object.getPrototypeOf(someobject)` and there is a `Object.setPrototypeOf(obj, prototype)`.
When we try to access a property, the engine looks in the objects, then the prototype, then that one's prototype, etc.
So objects inherit all properties of the prototypes chain.

(Note: The `func.prototype` property of functions specifies the [[Prototype]] to be assigned to **all** instances of objects created by the given function when used as a constructor.)

## Classes

## TypeScript

* npm install -g typescript
* tsc
 
tsc on .ts files creates js files. 
without changes TS will ensure number of function args are the same

Primitive types:

string, number and boolean
string[]
any

let davevar: string = 'sausage';

Parameter and return type annotations:

function doStuff(somevalue: string) : string {
  return somevalue + 'somesuffix';
}

Object type (? makes that property optional)

function printName(obj: { first: string; last?: string }) {

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

