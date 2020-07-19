# React

React, created by Facebook, is an open-source JavaScript library for building user interfaces. It is used to create components, handle state and props, utilize event listeners and certain life cycle methods to update data as it changes.

React combines HTML with JavaScript functionality to create its own markup language, JSX. This section will introduce you to all of these concepts and how to implement them for use with your own projects.

## Create a Simple JSX ElementPassed

React uses a syntax extension of JavaScript called JSX that allows you to write HTML directly within JavaScript. This has several benefits. It lets you use the full programmatic power of JavaScript within HTML, and helps to keep your code readable. For the most part, JSX is similar to the HTML that you have already learned, however there are a few key differences that will be covered throughout these challenges.

For instance, because JSX is a syntactic extension of JavaScript, you can actually write JavaScript directly within JSX. To do this, you simply include the code you want to be treated as JavaScript within curly braces: { 'this is treated as JavaScript code' }. Keep this in mind, since it's used in several future challenges.

However, because JSX is not valid JavaScript, JSX code must be compiled into JavaScript. The transpiler Babel is a popular tool for this process. For your convenience, it's already added behind the scenes for these challenges. If you happen to write syntactically invalid JSX, you will see the first test in these challenges fail.

It's worth noting that under the hood the challenges are calling ReactDOM.render(JSX, document.getElementById('root')). This function call is what places your JSX into React's own lightweight representation of the DOM. React then uses snapshots of its own DOM to optimize updating only specific parts of the actual DOM.

### Instructions

The current code uses JSX to assign a div element to the constant JSX. Replace the div with an h1 element and add the text Hello JSX! inside it.

```
const JSX = <h1>Hello JSX!</h1>;
```

## Create a Complex JSX ElementPassed

One important thing to know about nested JSX is that it must return a single element.

**Valid JSX:**
```
<div>
  <p>Paragraph One</p>
  <p>Paragraph Two</p>
  <p>Paragraph Three</p>
</div>
```

**Invalid JSX:**
```
<p>Paragraph One</p>
<p>Paragraph Two</p>
<p>Paragraph Three</p>
```


### Instructions

Define a new constant JSX that renders a div which contains the following elements in order:

An h1, a p, and an unordered list that contains three li items. You can include any text you want within each element.

>**Note:** When rendering multiple elements like this, you can wrap them all in parentheses, but it's not strictly required. Also notice this challenge uses a div tag to wrap all the child elements within a single parent element. If you remove the div, the JSX will no longer transpile. Keep this in mind, since it will also apply when you return JSX elements in React components.

```typescript jsx
const JSX = (<div>
                <h1>Header</h1>
                <p>Para</p>
                <ul>
                    <li>List 1</li>
                    <li>List 2</li>
                    <li>List 3</li>
                </ul>
            </div>
            );
```

## Add Comments in JSXPassed

To put comments inside JSX, you use the syntax {/* */} to wrap around the comment text.

```typescript jsx
const JSX = (
  <div>
  {/* This is a Comment */}
    <h1>This is a block of JSX</h1>
    <p>Here's a subtitle</p>
  </div>
);
```

## Render HTML Elements to the DOM

ReactDOM offers a simple method to render React elements to the DOM which looks like this: ReactDOM.render(componentToRender, targetNode), where the first argument is the React element or component that you want to render, and the second argument is the DOM node that you want to render the component to.

### Instructions

The code editor has a simple JSX component. Use the ReactDOM.render() method to render this component to the page. You can pass defined JSX elements directly in as the first argument and use document.getElementById() to select the DOM node to render them to. There is a div with id='challenge-node' available for you to use. Make sure you don't change the JSX constant.

```typescript jsx
const JSX = (
  <div>
    <h1>Hello World</h1>
    <p>Lets render this to the DOM</p>
  </div>
);
// change code below this line
ReactDOM.render(JSX, document.getElementById('challenge-node'));
```

## Define an HTML Class in JSXPassed

One key difference in JSX is that you can no longer use the word class to define HTML classes. This is because class is a reserved word in JavaScript. Instead, JSX uses className.

In fact, the naming convention for all HTML attributes and event references in JSX become camelCase. For example, a click event in JSX is onClick, instead of onclick. Likewise, onchange becomes onChange. While this is a subtle difference, it is an important one to keep in mind moving forward.

### Instructions

Apply a class of myDiv to the div provided in the JSX code.

```typescript jsx
const JSX = (
  <div className="myDiv">
    <h1>Add a class to this div</h1>
  </div>
);
```

## Learn About Self-Closing JSX Tags

Any JSX element can be written with a self-closing tag, and every element must be closed. The line-break tag, for example, must always be written as ```<br />``` in order to be valid JSX that can be transpiled. A ```<div>```, on the other hand, can be written as ```<div />``` or ```<div></div>```. The difference is that in the first syntax version there is no way to include anything in the <div />.

```typescript jsx
const JSX = (
  <div>
    <h2>Welcome to React!</h2> <br />
    <p>Be sure to close all tags!</p>
    <hr />
  </div>
);
```

## Create a Stateless Functional Component

There are two ways to create a React component. 
* Javascript Function that returns null or JSX
* ES6 Class

### JavaScript function. Defining a component in this way creates a stateless functional component. 

A stateless component as one that can receive data and render it, but does not manage or track changes to that data. 

To create a component with a function, you simply write a JavaScript function that returns either JSX or null. 

>**Note**: One important thing to note is that React requires your function name to begin with a capital letter.

```typescript jsx
// After being transpiled, the <div> will have a CSS class of 'customClass'
const DemoComponent = function() {
  return (
    <div className='customClass' />
  );
};
```

### ES6 class syntax

In the following example, Kitten extends React.Component:

```typescript jsx
class Kitten extends React.Component {
  constructor(props) {
    super(props);
  }

  render() {
    return (
      <h1>Hi</h1>
    );
  }
}
```

This creates an ES6 class Kitten which extends the React.Component class. So the Kitten class now has access to many useful React features, such as local state and lifecycle hooks.

Notice the Kitten class has a constructor defined within it that calls super(). It uses super() to call the constructor of the parent class, in this case React.Component.

It is best practice to call a component's constructor with super, and pass props to both. This makes sure the component is initialized properly. 

#### Instructions

MyComponent is defined in the code editor using class syntax. Finish writing the render method so it returns a div element that contains an h1 with the text Hello React!.

```jsx harmony
class MyComponent extends React.Component {
  constructor(props) {
    super(props);
  }
  render() {
    // change code below this line
    return(
      <div><h1>Hello React!</h1></div>
    );
    // change code above this line
  }
};
```

## Create a Component with Composition

Now we will look at how we can compose multiple React components together. Imagine you are building an App and have created three components, a Navbar, Dashboard, and Footer.

To compose these components together, you could create an App parent component which renders each of these three components as children. To render a component as a child in a React component, you include the component name written as a custom HTML tag in the JSX. For example, in the render method you could write:

```jsx harmony
return (
 <App>
  <Navbar />
  <Dashboard />
  <Footer />
 </App>
)
```

When React encounters a custom HTML tag that references another component (a component name wrapped in ```< />``` like in this example), it renders the markup for that component in the location of the tag. This should illustrate the parent/child relationship between the App component and the Navbar, Dashboard, and Footer.

### Instructions

In the code editor, there is a simple functional component called ChildComponent and a class component called ParentComponent. Compose the two together by rendering the ChildComponent within the ParentComponent. Make sure to close the ChildComponent tag with a forward slash.

Note: ChildComponent is defined with an ES6 arrow function because this is a very common practice when using React. However, know that this is just a function. 

```jsx harmony
{/* const ChildComponent = function() { */}
const ChildComponent = () => {
  return (
    <div>
      <p>I am the child</p>
    </div>
  );
};

class ParentComponent extends React.Component {
  constructor(props) {
    super(props);
  }
  render() {
    return (
      <div>
        <h1>I am the parent</h1>
        { /* change code below this line */ }
        <ChildComponent />
        { /* change code above this line */ }
      </div>
    );
  }
};
```

## Use React to Render Nested Components

Component composition is one of React's powerful features. When you work with React, it is important to start thinking about your user interface in terms of components like the App example in the last challenge. You break down your UI into its basic building blocks, and those pieces become the components. This helps to separate the code responsible for the UI from the code responsible for handling your application logic. It can greatly simplify the development and maintenance of complex projects.

### Instructions

There are two functional components defined in the code editor, called TypesOfFruit and Fruits. Take the TypesOfFruit component and compose it, or nest it, within the Fruits component. Then take the Fruits component and nest it within the TypesOfFood component. The result should be a child component, nested within a parent component, which is nested within a parent component of its own!

1. The TypesOfFood component should return a single div element.
1. The TypesOfFood component should return the Fruits component.
1. The Fruits component should return the TypesOfFruit component.
1. The TypesOfFruit component should return the h2 and ul elements.

```jsx harmony
const TypesOfFruit = () => {
  return (
    <div>
      <h2>Fruits:</h2>
      <ul>
        <li>Apples</li>
        <li>Blueberries</li>
        <li>Strawberries</li>
        <li>Bananas</li>
      </ul>
    </div>
  );
};

const Fruits = () => {
  return (
    <div>
      { /* calls the first fucntion that passes a div */ }
      <TypesOfFruit />
    </div>
  );
};

class TypesOfFood extends React.Component {
  constructor(props) {
    super(props);
  }

  render() {
    return (
      <div>
        <h1>Types of Food:</h1>
        { /* gets Fruits which gets TypesOfFruit */ }
        <Fruits />
      </div>
    );
  }
};
```

## Compose React Components

Within other components, you can render 
1. JSX elements
2. stateless functional components
3. and ES6 class components

### Instructions



In the code editor, the TypesOfFood component is already rendering a component called Vegetables. Also, there is the Fruits component from the last challenge.

Nest two components inside of Fruits — first NonCitrus, and then Citrus. Both of these components are provided for you behind the scenes. Next, nest the Fruits class component into the TypesOfFood component, below the h1 header and above Vegetables. The result should be a series of nested components, which uses two different component types.

1. The TypesOfFood component should return a single div element.
1. The TypesOfFood component should return the Fruits component.
1. The Fruits component should return the NonCitrus component and the Citrus component.
1. The TypesOfFood component should return the Vegetables component below the Fruits component.

```jsx harmony
const NonCitrus = () => {
  return (
    <ul>
    <li>Apple</li>
    <li>Mango</li>
    </ul>
  );
}
const Citrus = () => {
  return (
    <ul>
    <li>Lemon</li>
    <li>Orange</li>
    </ul>
  );
}
class Fruits extends React.Component {
  constructor(props) {
    super(props);
  }
  render() {
    return (
      <div>
        <h2>Fruits:</h2>
        { /* change code below this line */ }
        <h3>Non Citrus:</h3>
        <NonCitrus />
        <h3>Citrus:</h3>
        <Citrus />
      </div>
    );
  }
};

class TypesOfFood extends React.Component {
  constructor(props) {
     super(props);
  }
  render() {
    return (
      <div>
        <h1>Types of Food:</h1>
        <Fruits />
        <Vegetables />
      </div>
    );
  }
};

```

## Render a Class Component to the DOM

React components are passed into ReactDOM.render() a little differently than JSX elements. For JSX elements, you pass in the name of the element that you want to render. However, for React components, you need to use the same syntax as if you were rendering a nested component, for example ReactDOM.render(<ComponentToRender />, targetNode). You use this syntax for both ES6 class components and functional components.

### Instructions

Both the Fruits and Vegetables components are defined for you behind the scenes. Render both components as children of the TypesOfFood component, then render TypesOfFood to the DOM. There is a div with id='challenge-node' available for you to use.

1. The TypesOfFood component should return a single div element.
1. The TypesOfFood component should render the Fruits component after the h1 element.
1. The TypesOfFood component should render the Vegetables component after Fruits.
1. The TypesOfFood component should render to the DOM within the div with the id challenge-node.

```jsx harmony
class TypesOfFood extends React.Component {
  constructor(props) {
    super(props);
  }
  render() {
    return (
      <div>
        <h1>Types of Food:</h1>
        {/* change code below this line */}
        <Fruits />
        <Vegetables />
        {/* change code above this line */}
      </div>
    );
  }
};

// change code below this line
ReactDOM.render(<TypesOfFood />, document.getElementById("challenge-node"));
```

## Write a React Component from Scratch

Define a class MyComponent that extends React.Component. Its render method should return a div that contains an h1 tag with the text: My First React Component! in it. Use this text exactly, the case and punctuation matter. Make sure to call the constructor for your component, too.

Render this component to the DOM using ReactDOM.render(). There is a div with id='challenge-node' available for you to use.

### Instructions 
1. create a class
1. extend React.Component
1. define constuctor and take props as argument and call super(props)
1. render function with return of the JSX


```jsx harmony
// change code below this line
class MyComponent extends React.Component {
  constructor(props) {
      super(props);
  };
  render() {
    return (
      <div>
      <h1>My First React Component!</h1>
      </div>
    );
  };
};

ReactDOM.render(<MyComponent />, document.getElementById('challenge-node'));
```

## Pass Props to a Stateless Functional Component

