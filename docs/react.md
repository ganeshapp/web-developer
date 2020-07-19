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

In React, you can pass props, or properties, to child components. Say you have an App component which renders a child component called Welcome which is a stateless functional component. You can pass Welcome a user property by writing:
 
```jsx harmony
<App>
  <Welcome user='Mark' />
</App>
``` 

You use custom HTML attributes created by you and supported by React to be passed to the component. In this case, the created property user is passed to the component Welcome. Since Welcome is a stateless functional component, it has access to this value like so:

```jsx harmony
const Welcome = (props) => <h1>Hello, {props.user}!</h1>
```

### Instructions

There are Calendar and CurrentDate components in the code editor. When rendering CurrentDate from the Calendar component, pass in a property of date assigned to the current date from JavaScript's Date object. Then access this prop in the CurrentDate component, showing its value within the p tags. Note that for prop values to be evaluated as JavaScript, they must be enclosed in curly brackets, for instance date={Date()}.

1. The Calendar component should return a single div element.
1. The second child of the Calendar component should be the CurrentDate component.
1. The CurrentDate component should have a prop called date.
1. The date prop of the CurrentDate should contain a string of text.
1. The date prop should be generated by calling Date()
1. The CurrentDate component should render the value from the date prop in the p tag.

```jsx harmony
const CurrentDate = (props) => {
  return (
    <div>
      { /* change code below this line */ }
      <p>The current date is: {props.date}</p>
      { /* change code above this line */ }
    </div>
  );
};

class Calendar extends React.Component {
  constructor(props) {
    super(props);
  }
  render() {
    return (
      <div>
        <h3>What date is it?</h3>
        { /* change code below this line */ }
        <CurrentDate date={Date()}/>
        { /* change code above this line */ }
      </div>
    );
  }
};
```

## Pass an Array as Props

To pass an array to a JSX element, it must be treated as JavaScript and wrapped in curly braces.

```jsx harmony
<ParentComponent>
  <ChildComponent colors={["green", "blue", "red"]} />
</ParentComponent>
```

The child component then has access to the array property colors. Array methods such as join() can be used when accessing the property. ```const ChildComponent = (props) => <p>{props.colors.join(', ')}</p>``` This will join all colors array items into a comma separated string and produce: ```<p>green, blue, red</p>```

### Instructions

There are List and ToDo components in the code editor. When rendering each List from the ToDo component, pass in a tasks property assigned to an array of to-do tasks, for example ```["walk dog", "workout"]```. Then access this tasks array in the List component, showing its value within the p element. Use join(", ") to display the props.tasksarray in the p element as a comma separated list. Today's list should have at least 2 tasks and tomorrow's should have at least 3 tasks.

1. The ToDo component should return a single outer div.
1. The third child of the ToDo component should be an instance of the List component.
1. The fifth child of the ToDo component should be an instance of the List component.
1. Both instances of the List component should have a property called tasks and tasks should be of type array.
1. The first List component representing the tasks for today should have 2 or more items.
1. The second List component representing the tasks for tomorrow should have 3 or more items.
1. The List component should render the value from the tasks prop in the p tag.

```jsx harmony
const List = (props) => {
  { /* change code below this line */ }
  return <p>{props.tasks.join(', ')}</p>
  { /* change code above this line */ }
};

class ToDo extends React.Component {
  constructor(props) {
    super(props);
  }
  render() {
    return (
      <div>
        <h1>To Do Lists</h1>
        <h2>Today</h2>
        { /* change code below this line */ }
        <List tasks={['finish lesson 1','finish lesson 2']}/>
        <h2>Tomorrow</h2>
        <List tasks={['finish lesson 3','finish lesson 4', 'finish lesson 5']}/>
        { /* change code above this line */ }
      </div>
    );
  }
};

```

## Use Default Props

React also has an option to set default props. You can assign default props to a component as a property on the component itself and React assigns the default prop if necessary. This allows you to specify what a prop value should be if no value is explicitly provided. For example, if you declare MyComponent.defaultProps = { location: 'San Francisco' }, you have defined a location prop that's set to the string San Francisco, unless you specify otherwise. React assigns default props if props are undefined, but if you pass null as the value for a prop, it will remain null.

### Instructions

The code editor shows a ShoppingCart component. Define default props on this component which specify a prop items with a value of 0.

```jsx harmony
const ShoppingCart = (props) => {
  return (
    <div>
      <h1>Shopping Cart Component</h1>
    </div>
  )
};
// change code below this line
ShoppingCart.defaultProps = {items: 0};
```

## Override Default Props

The ShoppingCart component now renders a child component Items. This Items component has a default prop quantity set to the integer 0. Override the default prop by passing in a value of 10 for quantity.

>Note: Remember that the syntax to add a prop to a component looks similar to how you add HTML attributes. However, since the value for quantity is an integer, it won't go in quotes but it should be wrapped in curly braces. For example, {100}. This syntax tells JSX to interpret the value within the braces directly as JavaScript.

```jsx harmony
const Items = (props) => {
  return <h1>Current Quantity of Items in Cart: {props.quantity}</h1>
}

Items.defaultProps = {
  quantity: 0
}

class ShoppingCart extends React.Component {
  constructor(props) {
    super(props);
  }
  render() {
    { /* change code below this line */ }
    return <Items quantity={10} />
    { /* change code above this line */ }
  }
};
```

## Use PropTypes to Define the Props You Expect

React provides useful type-checking features to verify that components receive props of the correct type. For example, your application makes an API call to retrieve data that you expect to be in an array, which is then passed to a component as a prop. You can set propTypes on your component to require the data to be of type array. This will throw a useful warning when the data is of any other type.

It's considered a best practice to set propTypes when you know the type of a prop ahead of time. You can define a propTypes property for a component in the same way you defined defaultProps. Doing this will check that props of a given key are present with a given type. Here's an example to require the type function for a prop called handleClick:

MyComponent.propTypes = { handleClick: PropTypes.func.isRequired }

In the example above, the PropTypes.func part checks that handleClick is a function. Adding isRequired tells React that handleClick is a required property for that component. You will see a warning if that prop isn't provided. Also notice that func represents function. Among the seven JavaScript primitive types, function and boolean (written as bool) are the only two that use unusual spelling. In addition to the primitive types, there are other types available. For example, you can check that a prop is a React element. Please refer to the [documentation](https://reactjs.org/docs/jsx-in-depth.html#specifying-the-react-element-type) for all of the options.

```jsx harmony
const Items = (props) => {
  return <h1>Current Quantity of Items in Cart: {props.quantity}</h1>
};

// change code below this line
Items.propTypes = {
  quantity: PropTypes.number.isRequired
};
// change code above this line

Items.defaultProps = {
  quantity: 0
};

class ShoppingCart extends React.Component {
  constructor(props) {
    super(props);
  }
  render() {
    return <Items />
  }
};
```

## Access Props Using this.props

The last several challenges covered the basic ways to pass props to child components. But what if the child component that you're passing a prop to is an ES6 class component, rather than a stateless functional component? The ES6 class component uses a slightly different convention to access props.

Anytime you refer to a class component within itself, you use the this keyword. To access props within a class component, you preface the code that you use to access it with this. For example, if an ES6 class component has a prop called data, you write {this.props.data} in JSX.

### Instructions

Render an instance of the ReturnTempPassword component in the parent component ResetPassword. Here, give ReturnTempPassword a prop of tempPassword and assign it a value of a string that is at least 8 characters long. Within the child, ReturnTempPassword, access the tempPassword prop within the strong tags to make sure the user sees the temporary password.

```jsx harmony
class ReturnTempPassword extends React.Component {
  constructor(props) {
    super(props);

  }
  render() {
    return (
        <div>
            { /* change code below this line */ }
            <p>Your temporary password is: <strong>{this.props.tempPassword}</strong></p>
            { /* change code above this line */ }
        </div>
    );
  }
};

class ResetPassword extends React.Component {
  constructor(props) {
    super(props);

  }
  render() {
    return (
        <div>
          <h2>Reset Password</h2>
          <h3>We've generated a new temporary password for you.</h3>
          <h3>Please reset this password from your account settings ASAP.</h3>
          { /* change code below this line */ }
          <ReturnTempPassword tempPassword="asdfghij"/>
          { /* change code above this line */ }
        </div>
    );
  }
};
```

## Review Using Props with Stateless Functional Components

1. Stateless functional component: Any function you write which accepts props and returns JSX.
1. Stateless component: Is a class that extends React.Component, but does not use internal state.
1. Stateful component: Is a class component that does maintain its own internal state. You may see stateful components referred to simply as components or React components.

A common pattern is to try to minimize statefulness and to create stateless functional components wherever possible. This helps contain your state management to a specific area of your application. In turn, this improves development and maintenance of your app by making it easier to follow how changes to state affect its behavior.

### Instructions

The code editor has a CampSite component that renders a Camper component as a child. Define the Camper component and assign it default props of { name: 'CamperBot' }. Inside the Camper component, render any code that you want, but make sure to have one p element that includes only the name value that is passed in as a prop. Finally, define propTypes on the Camper component to require name to be provided as a prop and verify that it is of type string.

```jsx harmony
class CampSite extends React.Component {
  constructor(props) {
    super(props);
  }
  render() {
    return (
      <div>
        <Camper name="gapp"/>
      </div>
    );
  }
};
// change code below this line
class Camper extends React.Component {
  constructor(props) {
    super(props);

  }
  render() {
    return (
      <div><p>{this.props.name}</p></div>
    );
  }
};

Camper.defaultProps = {name: 'CamperBot'};

Camper.propTypes = {name: PropTypes.string.isRequired};
```

## Create a Stateful Component
