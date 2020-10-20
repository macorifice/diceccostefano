## “Any fool can write code that a computer can understand. Good programmers write code that humans can understand.” — Martin Fowler

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
