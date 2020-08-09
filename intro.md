# React Nested Components

## Overview
* React components are independent and resuable piece of code
* Class components serve a similar purpose as functions, but work in isolation and returns JSX via a render function 
---
## Learning Objectives
* Understanding the anatomy of a basic React component
* Creating a basic class component
* Creating child components 
* Calling React child components inside the return of the parent component
---


## Vocabulary 
* React
* class component
* render
* return
* component call
* JSX
---

## What is JSX?
<h4>JSX is JavaScript flavored HTML that behaves almost like HTML with a couple small exceptions -- most notably JSX uses the syntax ```className``` rather than HTML's ```class``` because ```class``` is reserved for HTML. <br /><h4>

<h4>As the building block of React Components, you will be using JSX a lot. <h4>

---
## Nested Components
<h4>Nesting components allow us to call a component within the return of another component.<h4> 
<h4>Let's start with a new application: <h4>

```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
  <head>
    <meta charset="utf-8">
    <script src="https://unpkg.com/react@16/umd/react.development.js" crossorigin></script>
    <script src="https://unpkg.com/react-dom@16/umd/react-dom.development.js" crossorigin></script>
    <script src="https://unpkg.com/@babel/standalone/babel.min.js"></script>
    <title>Intro to React</title>

  </head>
  <body>

    <div id="react-container"></div>

    <script type="text/babel">
      class App extends React.Component{
        render(){
          return(
            <div></div>
          )
        }
      }
      const domContainer = document.querySelector('#react-container');
      ReactDOM.render(<App />, domContainer);
    </script>
  </body>
</html>
```

<h4>
We have set up an App component to return an empty div. 

First, let's look at the ```render()``` class method. Render only works in smart, class components, and is doing the rendering of our JSX to display the code that will go within our empty our empty div. 

Next, we have a ```return()``` which is similar to the built-in JS function ```return```. It is returning the content inside of the parentheses. In React, when working with smart components, we need the JSX to live inside a single tag, which goes inside the ```return()```, which lives inside the ```render(){}```.

In React, the component renders only one JSX element. Therefore, it is imperative to wrap all of your elements in a single containing tag. In the example above, we created an empty ```div``` to house the JSX code we will be writing. This is where we will nest our other components. 

Next, we will define another component class: 

```html
<script type="text/babel">
  class App extends React.Component{
    render(){
      return(
        <div></div>
      )
    }
  }

  class Content extends React.Component{
    render(){
      return(
        <div>
          <h1>Title</h1>
          <p>
            This is app content.
          </p>
        </div>
      )
    }
  }
  const domContainer = document.querySelector('#react-container')
  ReactDOM.render(<App />, domContainer)
</script>
```

<h4>Finally, we call the component within the main component. In our case, the App component: <h4>

```html
<script type="text/babel">
 class App extends React.Component{
   render(){
     return(
       <div>
         <Content />
       </div>
     )
   }
 }

 class Content extends React.Component{
   render(){
     return(
       <div>
         <h1>Title</h1>
         <p>
           This is app content.
         </p>
       </div>
     )
   }
 }
 const domContainer = document.querySelector('#react-container');
 ReactDOM.render(<App />, domContainer)
</script>
```

With that call to the Content component within the App component's render, we now have a nested component. This pattern allows us to start building more complex applications. But, at this stage it helps to have some project structure built into our app application. For that we will turn to  ```yarn create react-app **your app name**```. 


<h4>
---

## Challenge!
<h4>The goal of the following challenge is for you to practice nesting components and getting familiar with class based component syntax. 

Create a new HTML file. Copy the following code into your file:

```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
<head>
  <meta charset="utf-8">
  <script src="https://unpkg.com/react@16/umd/react.development.js" crossorigin></script>
  <script src="https://unpkg.com/react-dom@16/umd/react-dom.development.js" crossorigin></script>
  <script src="https://unpkg.com/@babel/standalone/babel.min.js"></script>
  <title>Intro to React</title>

</head>
<body>

  <div id="react-container"></div>

  <script type="text/babel">
    class App extends React.Component{
      render(){
        return(
          <h1>Hello React!</h1>
        )
      }
    }
    const domContainer = document.querySelector('#react-container')
    ReactDOM.render(<App />, domContainer)
  </script>
</body>
</html>
```

Here are your stories:
* As a user, I see a Header component with your name 
* As a user, I can see a Content component that contains a list of your top three favorite colors.
* As a user, I can see a Footer component with the names of you and someone you care about.
<h4>
---




