# 🧐 Di Cecco Stefano's blog 🤓

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

- **Community**
<img src='https://lh4.googleusercontent.com/gvhsxCvy1tMZSPqSU18Kx0MT3s-1z_G7Kw4CbpJVBrcf2U9dYQQWlxJS03vwc2A9GJ32kpUi0eTs-rzUtW2v2j0LS12y8qxBR9CuYUL3RbfLBC-PpIXeoqopFmb-HWzmbjDG6RPEWgFGn-sbhg' style="display: block; margin: auto;" />

- **Performance**

- **Learning curve**

- **Scalability**

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
