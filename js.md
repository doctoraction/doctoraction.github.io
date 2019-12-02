# Modern JS

## Misc

npm install -g (global)
npm install --savedev (?)
npx - executes without installion (!?)
  
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

