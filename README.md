## Welcome to Di Cecco Stefano's site

“Any fool can write code that a computer can understand. Good programmers write code that humans can understand.” — Martin Fowler

### Hello World – React

The simplest example of React is this:

```
ReactDOM.render(
<h1>Hello, world!</h1>,
document.getElementById("root")
);
```

### Create React app

Create React App is a comfortable environment for learning React, and is the best way to start building a new single-page application in React.

It sets up your development environment so that you can use the latest JavaScript features, provides a nice developer experience, and optimizes your app for production. You’ll need to have Node >= 8.10 and npm >= 5.6 on your machine. To create a project, run:

```
npx create-react-app my-app
cd my-app
npm start
```

Create React App doesn’t handle backend logic or databases; it just creates a frontend build pipeline, so you can use it with any backend you want. Under the hood, it uses Babel and webpack, but you don’t need to know anything about them.
