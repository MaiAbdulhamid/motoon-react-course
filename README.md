# motoon-react-course

## 1. Lecture #1

### 1.1 React Basics

- What is React?

React is a library for building user interfaces.

- Why would you use it?

To Answer Let's look at Vanilla Js and React Projects:


[Vanilla Js](https://codesandbox.io/s/vanilla-js-demo-6049kj).


[ReactJs](https://codesandbox.io/s/react-vs-vanilla-demo-uc08fv).


So when writing React code, you are writing code in a declarative way.
On the other hand, when writing vanilla JavaScript code, you are writing imperative code, not declarative code.


Declarative approach: it basically means that with React, you will not tell React that a certain HTML element should be created and inserted in a specific place on the user interface as you would be doing it on the user interface as you would be doing it with Vanilla JavaScript.

Imperative approach : is giving clear instructions, clear step-by-step instructions, what JavaScript and the browser should be doing.

- Editing First React App.
  Add a Forth button to [React App](https://codesandbox.io/s/first-react-app-start-7ec9fd) that displays the forth content in the array.

- React embraces a concept called components. React is all about components.
- What exactly is a component?
  React just picks up that concept of functions and of separating code across functions and translates it to the front end web application world where we built an entire user interface by splitting our code into multiple components which we then can mix and match as we need to.

  React Components: are independent and reusable bits of code.

- Creating a new React Project:


  ```$ npx create-next-app```

  Must have node js installed.

- What is JSX?
  JSX stands for JavaScript XML.

  HTML in the end is XML, you could say.

  JSX allows us to write HTML elements in JavaScript and place them in the DOM without any createElement()  and/or appendChild() methods.

  JSX converts HTML tags into react elements.

  JSX allows us to write HTML directly within the JavaScript code.

  JSX is an extension of the JavaScript language based on ES6, and is translated into regular JavaScript at runtime.

  With JSX:
  
  ```
    const myElement = <h1>I Love JSX!</h1>;

    const root = ReactDOM.createRoot(document.getElementById('root'));
    root.render(myElement); 

  ```

  Without JSX:

  ```
    const myElement = React.createElement('h1', {}, 'I do not use JSX!');
  
    const root = ReactDOM.createRoot(document.getElementById('root'));
    root.render(myElement);
  ```

- How the component written in react:

  [Starting Project](https://codesandbox.io/s/headless-platform-mdsdy6).

  [Final Project](https://codesandbox.io/s/distracted-gianmarco-gl88r8?file=/src/Question.js:332-373).

  What to learn?
   - Adding Basic CSS Styling
   - Outputting Dynamic Data & Working with Expressions in JSX
   - Passing Data via "props".
   - The Concept of "Composition" ("children props")
   - Organizing Component Files





  

