# ASP Chef

[ASP Chef](https://asp-chef.alviano.net/) is a simple, intuitive web app for analysing answer sets without having to deal with complex tools or programming languages...
well, excluding ASP!

ASP Chef inspired by [CyberChef](https://gchq.github.io/CyberChef/#input=UVZOUUlFTm9aV1lo), and as such it is designed to ease the creation of pipelines of operations over arrays of models rather than being an IDE or editor for ASP.

## Prerequisites

A modern browser!
[Firefox](https://www.mozilla.org/en-US/firefox/new/) is a good choice as it has no restriction on the length of URLs.
Large pipelines may hit the restriction on the URL length of other browsers due to the way ASP Chef encodes recipes in the URL.

No other software is needed as everything is run in the browser thanks to [SvelteKit](https://kit.svelte.dev/), [clingo-wasm](https://github.com/domoritz/clingo-wasm), and many other Javascript libraries.

## Usage

The UI comprises three vertical panels, namely the __Operations panel__, the __Recipe panel__ and the __I/O panel__.

__ASP Chef__ recipes constitute a pipeline where each step takes in input an array of models and provides in output an array of models;
actually, a model in this context is any valid output of ASP systems, that is, even ground terms can be elements of a model.

The recipe is composed by selecting ingredients from the __Operations panel__ and setting their options in the __Recipe panel__.
Popovers are shown for each operation to provide a minimal explanation on how to use it in a recipe. 

The pipeline starts by splitting the input of the recipe (given in the __I/O panel__) on occurrences of the _reserved_ character `§`.
Each part of the input is parsed and checked to be a valid model.
Upon termination, the output of the last step of the recipe is shown in the __I/O panel__. 

The recipe and its input are encoded in the URL, which can be used to restore the recipe and its input for future usage.
As the list of operations grows, and the operations are extended and modified, it is possible that a previously crafted recipe becomes incompatible with the current deployed version of ASP Chef.
While it is possible that in the future a mechanism to preserve retro-compatibility will be implemented, it must be noted that at the moment the main goal of ASP Chef is to ease the fast prototyping of ASP pipelines rather than their long terming usage. 

## Examples

### Billy the Kid

A problem from the [LP/CP Programming Contest 2019](https://github.com/lpcp-contest/lpcp-contest-2019).
It is described [here](https://github.com/lpcp-contest/lpcp-contest-2019/blob/master/billykid/billykid.md).
An ASP Chef recipe solving the problem and including a graphical representation of intermediate steps can be found
[here](https://asp-chef.alviano.net/#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!).

### Aquarium

A problem from the [LP/CP Programming Contest 2020](https://github.com/lpcp-contest/lpcp-contest-2020/).
It is described [here](https://github.com/lpcp-contest/lpcp-contest-2020/tree/master/problem-1).
An ASP Chef recipe solving the problem and including a graphical representation of the solution can be found
[here](https://asp-chef.alviano.net/#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!)

### Buttons and Scissors

A problem from the [LP/CP Programming Contest 2021](https://github.com/lpcp-contest/lpcp-contest-2021/).
It is described [here](https://github.com/lpcp-contest/lpcp-contest-2021/tree/main/problem-2).
An ASP Chef recipe solving the problem and including a graphical representation of intermediate steps can be found 
[here](https://asp-chef.alviano.net/#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!).

### Fortress

A problem from the [LP/CP Programming Contest 2022](https://github.com/lpcp-contest/lpcp-contest-2022/).
It is described [here](https://github.com/lpcp-contest/lpcp-contest-2022/tree/main/problem-1).
An ASP Chef recipe solving the problem and including a graphical representation of the solution can be found 
[here](https://asp-chef.alviano.net/#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!)

## Development

### Setup

Checkout the repository and run
```bash
$ npm install             # install dependencies
$ npx playwright install  # for E2E test automation
```

Link `clingo.wasm` as a static file with
```bash
$ mkdir -p static/dist; ln -s ../../node_modules/clingo-wasm/dist/clingo.wasm static/dist/
```

Start the development server on port 5188 with
```bash
$ npm run dev
```

Run E2E tests with one of the following commands:
```bash
$ npm run test                                 # all tests are run headless
$ npm run test tests/test.Something.ts         # tests from a single file
$ npm run test:headed                          # all tests, show the browser
$ npm run test:headed tests/test.Something.ts  # single file, show the browser
```

### Adding new operations

Create a component in `src/lib/operations` and link it in the component `<RecipePanel>`.

The operation must be associated with a unique name.
The file implementing the operation must be named as the operation itself, spaces excluded. 

The operation must define its default options and register itself in the `Recipe` class.
When instantiated as an ingredient, the operation will receive in input an array of models, and it is expected to produce in output an array of models.
If the operation must show something depending on the input it will receive, listeners must be used (see the __Output operation__).

The DOM content of the operation should just instantiate the generic `<Operation>` component with a minimal description to be shown as a _popover_ and the content to show when the operation is added as an ingredient.

To ease test automation it is strongly suggested to add `data-testid` attributes to I/O elements of interest.
To actually test an operation add a file in `tests/test.OperationName.ts` with the relevant testcases.
Again, to ease the testing of combinations of different operations implement a method in `tests/utils.ts` to add the operation as an ingredient with the provided options.  


## Contributors

* [Mario Alviano](https://alviano.net)
* Davide Cirimele
* Luis Angel Rodriguez Reiners