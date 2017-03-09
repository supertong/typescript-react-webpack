# React with Typescript and Webpack Hot Module Reloading

## Well, yes, this is another wheel, why?
Because I have a different car 🛒

I know there are already few similar repos out there, but when I tried them, none of them really meets what I want. There is currently no a official document on how to set this thing up, especially for the Hot Module Reloading part. I hope if you were in the same journey as I am, this is another reference you can look at.

## Things you can take away from this repo.
* Use `CheckerPlugin` from `awsome-typescript-loader`, otherwise it gives me wired errors when compiling Typescript.
* Install `@types/webpack` and `@types/webpack-env`, so that `module` and `module.hot` can be detected by Typescript.
* The following code snippet is neccessary for hot reloading.
```js
// Hot Module Replacement API
if (module.hot) {
  module.hot.accept('./App', () => {
    // Why .default? Because App is `export default App`
    const App = require('./App').default
    render(App)
  });
```

## What else?
Nothing.