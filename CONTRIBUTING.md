# Development Guide

We appreciate that you are ready to help build Time to Leave! Everything you need to create and modify the source code, from environment setup to package creation, is available here.

## Requirements

-   Node.js: version 14.15 or higher
-   git

## Choose branch to clone

You must first fork the main repository and clone it to your local computer in order to **contribute to the project**. 

You can clone straight from the main branch of repository if all you want to do is *build it locally*.

### Install dependencies

```bash
npm install
```

## Running Time to Leave

To run Time to Leave, after the steps above:

```bash
npm start
```

## Linting & formatting

Time to Leave uses several linting and formatting tools in order to guarantee that code is homogeneous and consistent.

### Running and Fixing issues

Run the following before committing to guarantee the code you changed/added follows these rules:

```bash
npm run lint-fix
```

This will automatically fix the lint issues too.
If you want to just check the potential issues, without modifying the code, use

```bash
npm run lint
```

### Specific lint checks

Each type of file is related to a lint rule, and those can be run separately:

```bash
# css
npm run lint:css

# Node and Javascript
npm run lint:eslint
npm run lint:standard

# markdown
npm run lint:markdown
```

## Tests

Time to Leave has tests that will verify the correctness of the flow using Jest. All tests are located in `__tests__` directory.
We have a workflow in the repository that will run all the tests when a Pull Request is submitted, and the change is only approved if the tests are passing.

### Run locally

To run all tests locally:

```bash
npm run test:jest
```

After running, you'll see a message with tests passed or failed with time elapsed.

The error message will tell you more on why it failed, in terms of what was expected and what was got.

#### Running specific tests

You can run a specific test, when debugging, for example, by including the name of the test file in the command line. For example, to run only the `themes.js` tests, you can do:

```bash
npm run test:jest themes.js
```

Note: Although possible to run just a few tests, it's highly suggested that you run all tests when changing the code.

## Adding new dependencies

We are trying to keep exact versions in the package.json file so that every user that runs `npm install` gets similar results.
`npm install --save` adds packages by default with a `^` notation, that indicates freedom to install versions above the specified.
Thus, if you are adding a new dependency, you must use `npm install --save --save-exact` to add a specific version to the list of dependencies.

## Releasing

After building and testing, if a release is what you want, you may want to package the App by following commands:

```bash
# macOS
npm run package:mac

# Windows
npm run package:win

# Debian
npm run package:deb
```

These will create the respective file under `release-builds/` directory.

# Opening a Pull Request (PR)

All PRs are very welcome, and we'll do our best to review them as fast as possible.

Issues without activity for 7 days will be deemed stale and unassigned, unless justified.

Tip: Before pushing the PR, make sure the tests are passing, and that no lint issue is present.
