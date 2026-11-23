# Contributing

Thank you for your interest in improving the Coordination Polymer & MOF Structure Lab.

## Reporting a problem

Open a [GitHub issue](https://github.com/hafidzouihri-tech/cp-mof-structure-lab/issues) and include:

- the browser and its version;
- the CIF file, or its COD/CSD code, if you can share it;
- what you expected and what the program reported (a screenshot of the table row helps).

## Suggesting a feature

Open an issue describing the analysis you need and, if possible, a reference that defines it.

## Changing the code

1. Fork the repository and create a branch.
2. Edit `index.html`. The analysis core comes first in the script (everything before the `module.exports` line). The user interface follows.
3. Add or update a test in `tests/core.test.js` for any change to a computed value. Add a CIF to `examples/` if a new structure type is needed.
4. Run `npm test` and check that all tests pass.
5. Open the page in a browser, load the examples and press **Run analysis** to check that nothing in the interface broke.
6. Describe the change in `CHANGELOG.md` and open a pull request.

Please keep the program dependency-free and in a single HTML file, so that it keeps working offline.
