# Contributing to HyperApp

Thanks for taking the time to contribute! 🎉

HyperApp is an open source project and we love to receive contributions from our community. You can start to contribute in many ways, from writing tutorials or blog posts, improving the documentation, filing bug reports and requesting new features.

Following these guidelines helps to communicate that you respect the time of the developers developing this project, but don't be afraid to break the rules. Use your best judgment, and feel free to propose changes in a pull request.

All members of our community are expected to follow our [Code of Conduct](/CODE_OF_CONDUCT.md), please be welcoming and friendly in all your interactions with the project.

## Quickstart

Clone the project and install the dependencies.

```
git clone https://github.com/hyperapp/hyperapp
cd hyperapp && npm i
```

Run the tests.

```
npm run test
```

Build the minified bundle.

```
npm run build
```

## Filing Bugs

- Before submitting a bug report, search the issues for similar tickets. Your issue may have already been discussed or resolved. Feel free to add a comment to an existing ticket, even if it's closed.

- Determine which repository the problem should be reported in. If you have an issue with the website, you'll be better served in [hyperapp/website](https://github.com/hyperapp/website), etc. If you would like to share something cool you've made with HyperApp, check out [hyperapp/awesome](https://github.com/hyperapp/awesome-hyperapp).

- If you have a question or need help with something you are building, we recommend joining the [HyperApp Slack Team](https://hyperappjs.herokuapp.com).

- Treat others as you want to be treated. Be polite, be thorough in your title and report, don't leave out important details, describe your setup and include any relevant code with your issue. If you can create a live example on [CodePen](https://codepen.io) or [JSFiddle](https://jsfiddle.net) you'll help us save more time and find a solution faster.

- Use GitHub [fenced code blocks](https://help.github.com/articles/creating-and-highlighting-code-blocks/) to share your code. If your code has JSX in it, please use <samp>```jsx</samp> for accurate syntax highlighting.

## Code Style

- Prefer descriptive single-word variable / function names to single-letter names.

- Consider improving the [Implementation Notes](/docs/implementation-notes.md) section in the documentation before adding comments to the code.

- Format your code before adding a commit using [prettier](https://prettier.github.io/prettier) or running the <samp>format</samp> script.

  ```
  npm run format
  ```

- HyperApp is written in ES5 with the exception of the ES6 module syntax.

- HyperApp is very small, so we prefer keeping all the moving parts inside as few files as possible. While this may change in the future, we don't intend to break the library into smaller modules.

- HyperApp currently supports IE10+. Make sure to check with [caniuse.com](https://caniuse.com) before adding an unsupported feature.

## Core Values

- HyperApp was born out of the attempt to do more with less. We have aggressively minimized the concepts you need to understand while remaining on par with what other frameworks can do.

- HyperApp's design is based on the Elm Architecture and application development is similar to React/Redux using a single immutable state tree.

- The API is minimal so you can spend your efforts learning functional frontend programming and not a particular API that may go out of style eventually.

- The ideal bundle size is 1 KB, but no more than 1.5 KB.

## Writing Tests

- We use [Babel](https://babeljs.io) and [Jest](http://facebook.github.io/jest) to run the tests.

- Feel free to create a new <samp>test/*.test.js</samp> file if none of the existing test files suits your test case.

- Tests usually create an application with [app](/docs/api.md#app) and check if the document.body.innerHTML matches some expected string. The app() call is async, so we use the [loaded](/docs/api.md#loaded) event to detect when the view has been attached to the document.

- HyperApp uses [requestAnimationFrame](https://developer.mozilla.org/en-US/docs/Web/API/window/requestAnimationFrame) under the hood, but it is not natively supported by Jest. For this reason you'll often see the following code at the top of a test file:

  ```js
  window.requestAnimationFrame = setTimeout
  ```
