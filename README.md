## “Any fool can write code that a computer can understand. Good programmers write code that humans can understand.” — Martin Fowler

### 5️⃣ A new state management in React - Recoil

Recoil is an experimental set of utilities for state management with React. Recoil lets you create a data-flow graph that flows from atoms (shared state) through selectors (pure functions) and down into your React components. Atoms are units of state that components can subscribe to. Selectors transform this state either synchronously or asynchronously.

- Atoms

Atoms are units of state. They're updateable and subscribable: when an atom is updated, each subscribed component is re-rendered with the new value. They can be created at runtime, too. Atoms can be used in place of React local component state. If the same atom is used from multiple components, all those components share their state.

Atoms are created using the atom function:
```
const fontSizeState = atom({
  key: 'fontSizeState',
  default: 14,
});
```

Atoms need a unique key, which is used for debugging, persistence, and for certain advanced APIs that let you see a map of all atoms. It is an error for two atoms to have the same key, so make sure they're globally unique. Like React component state, they also have a default value.

To read and write an atom from a component, we use a hook called useRecoilState. It's just like React's useState, but now the state can be shared between components:
```
function FontButton() {
  const [fontSize, setFontSize] = useRecoilState(fontSizeState);
  return (
    <button onClick={() => setFontSize((size) => size + 1)} style={{fontSize}}>
      Click to Enlarge
    </button>
  );
}
```

Clicking on the button will increase the font size of the button by one. But now some other component can also use the same font size:
```
function Text() {
  const [fontSize, setFontSize] = useRecoilState(fontSizeState);
  return <p style={{fontSize}}>This text will increase in size too.</p>;
}
```

- Selectors

A selector is a pure function that accepts atoms or other selectors as input. When these upstream atoms or selectors are updated, the selector function will be re-evaluated. Components can subscribe to selectors just like atoms, and will then be re-rendered when the selectors change.

Selectors are used to calculate derived data that is based on state. This lets us avoid redundant state, usually obviating the need for reducers to keep state in sync and valid. Instead, a minimal set of state is stored in atoms, while everything else is efficiently computed as a function of that minimal state. Since selectors keep track of what components need them and what state they depend on, they make this functional approach more efficient.

From the point of view of components, selectors and atoms have the same interface and can therefore be substituted for one another.

Selectors are defined using the selector function:
```
const fontSizeLabelState = selector({
  key: 'fontSizeLabelState',
  get: ({get}) => {
    const fontSize = get(fontSizeState);
    const unit = 'px';

    return `${fontSize}${unit}`;
  },
});
```
The get property is the function that is to be computed. It can access the value of atoms and other selectors using the get argument passed to it. Whenever it accesses another atom or selector, a dependency relationship is created such that updating the other atom or selector will cause this one to be recomputed.

In this fontSizeLabelState example, the selector has one dependency: the fontSizeState atom. Conceptually, the fontSizeLabelState selector behaves like a pure function that takes a fontSizeState as input and returns a formatted font size label as output.

Selectors can be read using useRecoilValue(), which takes an atom or selector as an argument and returns the corresponding value. We don't use the useRecoilState() as the fontSizeLabelState selector is not writeable (see the selector API reference for more information on writeable selectors):
```
function FontButton() {
  const [fontSize, setFontSize] = useRecoilState(fontSizeState);
  const fontSizeLabel = useRecoilValue(fontSizeLabelState);

  return (
    <>
      <div>Current font size: ${fontSizeLabel}</div>

      <button onClick={() => setFontSize(fontSize + 1)} style={{fontSize}}>
        Click to Enlarge
      </button>
    </>
  );
}
```

Clicking on the button now does two things: it increases the font size of the button while also updating the font size label to reflect the current font size.


### 4️⃣ State management in React - Redux

React bindings are not included in Redux by default. You need to install them explicitly:
```
npm install react-redux
```

Redux is a pattern and library for managing and updating application state, using events called "actions". It serves as a centralized store for state that needs to be used across your entire application, with rules ensuring that the state can only be updated in a predictable fashion.

Redux helps you manage "global" state - state that is needed across many parts of your application.

The patterns and tools provided by Redux make it easier to understand when, where, why, and how the state in your application is being updated, and how your application logic will behave when those changes occur. Redux guides you towards writing code that is predictable and testable, which helps give you confidence that your application will work as expected.

Redux helps you deal with shared state management, but like any tool, it has tradeoffs. There's more concepts to learn, and more code to write. It also adds some indirection to your code, and asks you to follow certain restrictions. It's a trade-off between short term and long term productivity.

Redux is more useful when:

- You have large amounts of application state that are needed in many places in the app
- The app state is updated frequently over time
- The logic to update that state may be complex
- The app has a medium or large-sized codebase, and might be worked on by many people

Not all apps need Redux. Take some time to think about the kind of app you're building, and decide what tools would be best to help solve the problems you're working on.

- React-Redux

Redux can integrate with any UI framework, and is most frequently used with React. React-Redux is our official package that lets your React components interact with a Redux store by reading pieces of state and dispatching actions to update the store.

- Redux Toolkit

Redux Toolkit is our recommended approach for writing Redux logic. It contains packages and functions that we think are essential for building a Redux app. Redux Toolkit builds in our suggested best practices, simplifies most Redux tasks, prevents common mistakes, and makes it easier to write Redux applications.

- Redux DevTools Extension

The Redux DevTools Extension shows a history of the changes to the state in your Redux store over time. This allows you to debug your applications effectively, including using powerful techniques like "time-travel debugging".


### 3️⃣ React is better than Angular?

|               | **React**     | **Angular** |
| ------------- | ------------- | --------  |
| **First release** | 2013          | 2016      |
| **Introduced by** | Facebook      | Google    |
| **Type of solution** | library    | framework |
| **Programming language used** | JavaScript (+ TypeScript support) | TypeScript |
| **DOM** | virtual DOM | regular DOM |
| **Architecture** | component-based | component-based |

First, the question is wrong! Because it’s not really possible to compare a UI library (React) and a framework (Angular).

Angular is a JavaScript open-source front-end framework. It’s developed by Google and dates back to 2010. This framework is based on TypeScript, a programming language that originates from JavaScript.

Although Angular has two versions – the first is Angular JS and the second is Angular 2 – when talking about this framework, front-end developers usually mean Angular 2 calling it just Angular. The latest 10th Angular update (Angular 10) was released in June 2020.

Angular is quite wide-spread, such well-known brand names as Forbes, Xbox, McDonald’s, PayPal, Telegram, Nike, and many others utilize Angular for their web app development.

React.js was released by Facebook in 2013 and since then it’s been quite popular among different world-known businesses. Instagram, WhatsApp, Netflix, Uber, Pinterest, and others use React for front-end development.

Many front-end developers argue on what React js is. Some say that it’s a library, others argue that it’s a framework. Wikipedia states that t React (also known as React.js or ReactJS) is a simple open-source JavaScript library. While all frameworks follow the MVC (Model-Viewer-Controller) paradigm, React accounts only for data representation. It means that it stands only for a V letter from MVC abbreviation.

There might be confusion between React and React Native as they are used for different purposes. React.js is mainly used for web development whereas React Native (a stand-alone open-source framework) is used for building mobile applications.

### 2️⃣ Create React app

Create React App is a comfortable environment for learning React, and is the best way to start building a new single-page application in React.

It sets up your development environment so that you can use the latest JavaScript features, provides a nice developer experience, and optimizes your app for production. You’ll need to have Node >= 8.10 and npm >= 5.6 on your machine. To create a project, run:

```
npx create-react-app my-app
cd my-app
npm start
```

Create React App doesn’t handle backend logic or databases; it just creates a frontend build pipeline, so you can use it with any backend you want. Under the hood, it uses Babel and webpack, but you don’t need to know anything about them.

### 1️⃣ Hello World – React

The simplest example of React is this:

```
ReactDOM.render(
<h1>Hello, world!</h1>,
document.getElementById("root")
);
```
