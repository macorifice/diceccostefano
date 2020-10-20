## “Any fool can write code that a computer can understand. Good programmers write code that humans can understand.” — Martin Fowler

### 3️⃣ - React is better than Angular?

<img src='https://diceccostefano.files.wordpress.com/2020/10/screenshot-2020-10-20-at-13.15.30.png' style="display: block; margin: auto;" />

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

- ***Google Trends* (React,Angular)**

<img src='https://lh4.googleusercontent.com/gvhsxCvy1tMZSPqSU18Kx0MT3s-1z_G7Kw4CbpJVBrcf2U9dYQQWlxJS03vwc2A9GJ32kpUi0eTs-rzUtW2v2j0LS12y8qxBR9CuYUL3RbfLBC-PpIXeoqopFmb-HWzmbjDG6RPEWgFGn-sbhg' style="display: block; margin: auto;" />

### 2️⃣ - Create React app

<img src='https://diceccostefano.files.wordpress.com/2020/10/screenshot-2020-10-20-at-13.02.48.png' style="display: block; margin: auto;" />

Create React App is a comfortable environment for learning React, and is the best way to start building a new single-page application in React.

It sets up your development environment so that you can use the latest JavaScript features, provides a nice developer experience, and optimizes your app for production. You’ll need to have Node >= 8.10 and npm >= 5.6 on your machine. To create a project, run:

```
npx create-react-app my-app
cd my-app
npm start
```

Create React App doesn’t handle backend logic or databases; it just creates a frontend build pipeline, so you can use it with any backend you want. Under the hood, it uses Babel and webpack, but you don’t need to know anything about them.

### 1️⃣ - Hello World – React

<img src='https://diceccostefano.files.wordpress.com/2020/10/screenshot-2020-10-20-at-12.39.44.png' style="display: block; margin: auto;" />

The simplest example of React is this:

```
ReactDOM.render(
<h1>Hello, world!</h1>,
document.getElementById("root")
);
```
