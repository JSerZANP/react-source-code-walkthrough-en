# render()

Here is the code : [ref](https://github.com/facebook/react/blob/12adaffef7105e2714f82651ea51936c563fe15c/packages/react-dom/src/client/ReactDOMLegacy.js#L287-L315)

```js
export function render(
  element: React$Element<any>,
  container: Container,
  callback: ?Function,
) {
  invariant(
    isValidContainer(container),
    'Target container is not a DOM element.',
  );
  if (__DEV__) {
    const isModernRoot =
      isContainerMarkedAsRoot(container) &&
      container._reactRootContainer === undefined;
    if (isModernRoot) {
      console.error(
        'You are calling ReactDOM.render() on a container that was previously ' +
          'passed to ReactDOM.createRoot(). This is not supported. ' +
          'Did you mean to call root.render(element)?',
      );
    }
  }
  return legacyRenderSubtreeIntoContainer(
    null,
    element,
    container,
    false,
    callback,
  );
}
```

Ignore the assertions and code for DEV mode, `render()` actually only calls `legacyRenderSubtreeIntoContainer()`.

From the name we can see that this is legacy code, meaning there is/will be something new, but we'll get to know it later.

Now let's take a look at [legacyRenderSubtreeIntoContainer()](./legacyRenderSubtreeIntoContainer.md)
