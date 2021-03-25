# 1. Debug Hello World.

Let's start with the classic Hello World program.

## 1.1 Setting Up

As React team has mentioned in [How to Contribute](https://reactjs.org/docs/how-to-contribute.html),
all you need to do is:

```
> git clone git@github.com:facebook/react.git`
> yarn build react/index,react-dom/index --type=UMD
```

Then open `fixtures/packaging/babel-standalone/dev.html` in Chrome, we can see the familiar Hello World.

![](../static/1.1.png)

1. development version of React and ReactDOM, built from yarn
2. babel.js to support JSX syntax
3. real DOM container holding Hello World
4. raw React code with JSX in `type="text/babel"`

Babel is used to transform JSX code on the fly, we could just ignore it.

How exactly does `Hello World!` become visible here?

## 1.2
