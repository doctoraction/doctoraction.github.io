# Modern JS

## Misc

npm install -g (installs packages globally to home directory)

npm install --savedev (something v similar to --save)

npx - executes without installation (!?)

Once you#ve installed a package globaly you don;'t need to run npm ...
  eg: create-react-app some_name not npm create-react-app some_name

## Functions

## Types, objects, Arrays ...

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

