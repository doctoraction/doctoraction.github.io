# Modern JS

## Misc

npm install -g (installs packages globally to home directory)

npm install --savedev (something v similar to --save)

npx - executes without installation (!?)

Once you#ve installed a package globaly you don;'t need to run npm ...
  eg: create-react-app some_name not npm create-react-app some_name
  
## Arrays and objects

## Classes

## TypeScript

## Functions
  
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

