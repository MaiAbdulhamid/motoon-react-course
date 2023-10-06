# motoon-react-course

## Lecture #1

### 1.1 JS Refresher

- [Starting Project](https://codesandbox.io/s/javascript-refresher-start-forked-3587t8).

- [React Project](https://codesandbox.io/s/react-vs-vanilla-demo-forked-h4ftkq).

-  Adding JavaScript To A Page & How React Projects Differ:

   - You can either put your JavaScript code between such script tags, or you can use those script tags to import JavaScript files.

   ```js
    <head>
      <meta charset="utf-8">
      <title>TEST</title>
      <script  type="module" src="script.js" defer></script>
    </head>
   ```

   ```js
     <script>
       alert("Hello")
     </script>
   ```

  - The `defer` attribute, to make sure that the script that will be imported, will only be executed after the rest of the HTML document has been read and parsed.
  - The `type="module"` attribute on the script tag makes sure that this JavaScript file is treated as a JavaScript module. And if you are treating your JavaScript files as modules, this unlocks one very important new syntax. The import syntax, where you can import code from script A into script B.
  - We are not use import scripts into React projects.
  - React Projects Use a Build Process: by the React Scripts library. And this is actually a library that's not going to be executed in the browser or that's used by React once it's running in the browser, but instead this React Scripts package provides a bunch of tools that take your code and transform it behind the scenes before it's then injected into the browser.
  - **Why does the code need to be transformed?**

    for two main reasons:
    1.  Because React code uses this special `JSX` feature. It's transformed to something JavaScript knows before the code gets executed in the browser.
    2.  The code you write would not be optimized for production, it would not be minified, for example. `Minification` simply means that, for example, names of variables or functions are shortened to reduce the amount of JavaScript code that's served to the user.

- "import" & "export"
  - Assume that we have two files, File A which contains a variable that used in File B.
  - File A.js Code:
 
    ```js
      const name = "Mai";
      export const age = 28;
      export default name;
    ```
  - File B.js Code:
    ```js
      import username, {age as userAge} from "./A.js";
      alert(`Hello ${username} Your age is ${userAge}`)
    ```
  - There is snother way to import:
    ```js
      import * as user from "./A.js";
      alert(`Hello ${user.default} Your age is ${user.age}`)
    ```
- Revisiting Variables & Values:

  ![Types and Values](https://user-images.githubusercontent.com/35450622/257054115-63507ef7-7aa6-4056-9f17-716ab395a227.png)
  
  - You use variables because they allow you to reuse a value and because they can help with code readability.
 
  ![Variables](https://user-images.githubusercontent.com/35450622/257054490-313b658d-1bfd-49fd-bcb0-cdaf87ed9970.png)

  - Define Variables Rules:
    ```js
      let name = "Mai";
      name = "Ahmed";

      const age = 28;
    ```
  ![Rules](https://user-images.githubusercontent.com/35450622/257054885-e782d71d-b8e8-4844-883e-cb9b02e8239a.png)

- Functions & Parameters
   - simply is that you're defining some code that's not executed immediately, but instead, at some point in the future when you call the function.
   - create a function in JavaScript:
     1.  Declaration Function
        ```js
            function sum(a, b) { return a + b; }
        ```
     2. Expression Function
        ```js
            //Can be named:
            (function sum(a, b) { return a + b; });
            
            // Or anonymous (AVOID):
            (function(a, b) { return a + b; });
            
            // Or assigned to a variable
            const sum = function sum(a, b) { return a + b; })

           //Calling
           sum(1+2)
        ```
     3. Arrow Function
    
        ```js
            // Regular:
            (a, b) => { return a + b };
            
            // Single argument, one line return:
            name => name.split(' ')
            
            // Multi arguments, one line return:
            (a, b) => a + b
            
            // Single argument, full body:
            name => { return name.split(' '); }
        ```
    
- Objects & Classes
  - Objects
    ```js
      const user = {
         name: 'Mai',
         age: 28,
         greet(){
          console.log(`Hello ${this.name}`)
         }   
       };
       user.greet();
       console.log(user.name);
    ```
  - Classes is a blueprints for objects
    ```js
    class User {
        constructor(name, age) {
          this.name = name;
          this.age = age;
        }
        greet(){
          console.log(`Hello ${this.name}`)
        }
    }
    const user = new User('Mai', 28)
    user.greet()
    ```
- Arrays & Array Methods
  - Arrays are objects, but they are special kinds of objects.
  - the idea behind an array simply is that you can create a list of values.
    ```js
      const cars = ["Saab", "Volvo", "BMW"];
      console.log(cars[0])

      const modifiedCars = cars.map(car => car + '!');
      console.log(modifiedCars)
    ```
  - `map()` allows you to transform every item in an array to another item.

- Destructuring
  - Destructuring in Arrays:
  ```js
   let a, b, rest;
   let array = [10, 20]
   [a, b] = array;
   
   console.log(a);
   console.log(array[0])
   // Expected output: 10
   
   console.log(b);
   console.log(array[1])
   // Expected output: 20
   
   [a, b, ...rest] = [10, 20, 30, 40, 50];
   
   console.log(rest);
   // Expected output: Array [30, 40, 50]
  ```
  - Destructuring in Objects:
  ```js
   const obj = { a: 1, b: 2 };
   const { a, b } = obj;
   // is equivalent to:
   // const a = obj.a;
   // const b = obj.b;
  ```
  - Destructuring in Function Parameter:
  ```js
   function storeOrder({id, currency}) { // destructuring
     localStorage.setItem('id', id);
     localStorage.setItem('currency', currency);
   }
  ```

- The Spread Operator
  - It pulls out values from an array, and adds them as separate, comma separated values to a new array.
  ```js
   function sum(x, y, z) {
     return x + y + z;
   }
   
   const numbers = [1, 2, 3];
   
   console.log(sum(...numbers));
  ```
- Control Structures:
  - If/else
  ```js
   function testNum(a) {
     let result;
     if (a > 0) {
       result = 'positive';
     } else {
       result = 'NOT positive';
     }
     return result;
   }
   
   console.log(testNum(-5));
   // Expected output: "NOT positive"
  ```
  - for - loops through a block of code a number of times
  ```js
   for (let i = 0; i < cars.length; i++) {
     text += cars[i] + "<br>";
   }
  ```
  
  - for/in - loops through the properties of an object
    ```js
      const object = { a: 1, b: 2, c: 3 };
      
      for (const property in object) {
        console.log(`${property}: ${object[property]}`);
      }
      
      // Expected output:
      // "a: 1"
      // "b: 2"
      // "c: 3"
    ```
  - for/of - loops through the values of an iterable object
    ```js
      const array1 = ['a', 'b', 'c'];
      
      for (const element of array1) {
        console.log(element);
      }
      
      // Expected output: "a"
      // Expected output: "b"
      // Expected output: "c"
    ```
- Reference vs Primitive Values
   - [Article](https://www.freecodecamp.org/news/primitive-vs-reference-data-types-in-javascript/)
  
### 1.2 React Basics

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
 
## Lecture #2

### 2.1 Practice

- [Starting Project](https://codesandbox.io/s/practice-cmp-start-forked-qll42n?file=/src/hints:39-51).

![Tasks](https://user-images.githubusercontent.com/35450622/273007910-15b64355-39ab-479b-8591-1cb337fef731.png)

### 2.2 React Events

- So instead of adding a listener as we would normally do it, which would be the imperative way of doing that.
```js
function App() {
  document.getElementById('button').addEventListner('click', () => {
      ///Do something
   })
  return (
    <div className="app">
      <h1>"Project: FAQ/Accordion"</h1>
      <button id='button' >Change Title</button>
    </div>
  );
}
```
- Adding Events: On all built-in HTML elements, like divs and h2, and especially all the buttons and so on,we have full access to all these native DOM events which we can listen to.
- All these event handler props, want a function as a value, a function passed as a value for `onClick`.
```js
function App() {
  return (
    <div className="app">
      <h1>"Project: FAQ/Accordion"</h1>
      <button onClick={() => console.log("clickced")} >Change Title</button>
    </div>
  );
}
```
- We just point at handler Function. We don't execute it here. You don't add parentheses.
- Because if you would add parentheses here, JavaScript would execute this when this line of code is being parsed. And this line of code is being parsed when the JSX code is returned.
- So it's then not executing clickHandler when the click occurs but when this JSX code is evaluated, and that would be too early.
- We pass a pointer at this function as a value to onClick, and then React basically memorizes this and executes the function for us whenever the click occurs.

  
- If we change title by Variable it will not work:
```js
function App() {
   let title = "Project: FAQ/Accordion";
   const clickButtonHandler = () => {
      title = 'Title Changed!!!'
      console.log("clickced")
   }
  return (
    <div className="app">
      <h1>{title}</h1>
      <button onClick={clickButtonHandler} >Change Title</button>
    </div>
  );
}
```
- Why?
   - keep in mind that your component is a function. the only special thing about that function, is that it returns JSX.
   - since it's a function someone has to call it, and you might notice that we never called our component functions, instead we just used these functions like HTML elements in this JSX code.
   - Well, the thing is, under the hood this is almost like a function call.
   - whenever react evaluates this JSX code, it will call these component functions. And these component functions stand to return JSX code, which is all the evaluated, up until there's no more JSX code to be evaluated.
   - And then it re-evaluates the overall result and translates that into DOM instructions which renders something like this on the screen.
   - The only problem with that is, that react never repeats that. React goes through all of that when the application is initially rendered, but thereafter it's done.
   - So we need a way of telling react that something changed and that a certain component should be re-evaluated.
   - So that we need `State`

### 2.3 State
- we import a function, which is called `useState`.
- this function allows us to define values as state where changes to these values should reflect in the component function being called again.

- How do we use this useState function though?
  
   - Inside of our component function and that's important, we have to do that inside of this function. We just call useState.
   - And useState is a so-called React hook.
   - All these React hooks can be recognized by the fact that they start with the word "use" in their name.
   - useState takes a default state value.
   - with useState we basically create a special kind of variable, you could say, a variable where changes will lead this component function to be called again.
   - we simply pass this innitial value as an argument to `useState`.
   - for that useState actually returns an array where the first value is the variable itself, the `current state` value., you could say, the value itself.And the second element in the array is that `updating function`.
     
- Why do we have this state updating function instead of assigning a new value like this?
   - The reason for that is, that calling this function does not just assign a new value to some variable, but that instead it is a special variable to begin with. It's managed by React somewhere in memory. And when we call this state updating function, this special variable will not just receive a new value but, the component function in which you called this state updating function. will be executed again.

#### Working with forms
```js
   <form>
     <div>
       <label>Title</label>
       <input type='text' />
     </div>
     <div>
       <label>Description</label>
       <textarea rows={6} />
     </div>
     <button type="submit">Add Question</button>
   </form>
```
- Styling form:
```
form div{
  display: flex;
  flex-direction: column;
  gap: 1rem;
  margin: 1rem 0;
}
form input, form textarea{
  width:70%;
  padding: 1rem;
  border: 1px solid #ddd;
  border-radius:10px
}
form button{
   margin: 1rem 0
}
```
- Submitting the form by `onSubmit` event handler.
- `e.preventDefault()`: prevents the reload.
- `console.log` data.
- How to clear input values? By listen to state value in each input. This is called **Two-way binding**.
- The Goal is to add item to the array of questions.By passing data from child to parent.
- **Lifting State Up**: concept of moving data from a child to a parent component by utilizing props to receive a function from the parent component which we call in the child component.
- App.js:
```js
import "./styles.css";
import Questions from "./Questions";
import NewQuestionForm from "./components/NewQuestionForm";

const DUMMY_QUESTIONS = [
   ...
];
const addQuestionHandelr = (question) => {
  console.log(question);
  const enteredQuestion = {
    ...question,
    id: Math.random().toString(),
  }
  console.log(enteredQuestion);
}
function App() {
   return (
    <div className="app">
      <h1>"Project: FAQ/Accordion"</h1>
      {/* Questions Goes Here */}
      <NewQuestionForm onAddQuestion={addQuestionHandelr} />
      <div className="container">
        <Questions questions={DUMMY_QUESTIONS} />
      </div>
    </div>
  );
}

export default App;
```
- Form.js:
```js
import { useState } from "react";
const initialValue = {
  title: "",
  description: ""
}
const NewQuestionForm = (props) => {
  const [userInput, setUserInput] = useState(initialValue);
  const inputChangeHandler = (type, value) => {
    if (type === "title") {
      setUserInput((prevState) => ({
        ...prevState,
        title: value
      }));
    }else{
      setUserInput((prevState) => ({
        ...prevState,
        description: value
      }));
    }
  };
  const onSubmitHandler = (e) => {
    e.preventDefault();
    props.onAddQuestion(userInput)
    setUserInput(initialValue)
  }
  return (
    <form onSubmit={onSubmitHandler}>
      <div>
        <label>Title</label>
        <input
          type="text"
          onChange={(e) => inputChangeHandler("description", e.target.value)}
        />
      </div>
      <div>
        <label>Description</label>
        <textarea
          rows={6}
          onChange={(e) => inputChangeHandler("title", e.target.value)}
        />
      </div>
      <button type="submit">Add Question</button>
    </form>
  );
};

export default NewQuestionForm;

```
- We are passing data up to some parent component because we either need that data directly in the app component
or because we then wanna pass that data down to another component via props.
-  **Derived state**: If you are setting a state that in the end is directly related to another state, you typically don't wanna manage this as a separate state. Instead you just want to add a new variable, a good old variable in your component function.
- So this here is a computed value, a value which we derive based on this state.
- **Uncontrolled Component**: in React are those in which form data is handled by the DOM.
- **Controlled components**: in React are those in which form data is handled by the component’s state.
- **Presentational or dumb component**: it doesn't have any internal state it's just there to output some data.
- **Stateful components**: If the component is responsible for managing some data, removing side effects, and contains states, this component is called a Stateful Component.




  

