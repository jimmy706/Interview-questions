# React interview questions

### Q1: What is virtual DOM?
> Difficulty : ⭐

**The virtual DOM (VDOM)** is an in-memory representation of Real DOM. The representation of a UI is kept in memory and synced with the “real” DOM. It’s a step that happens between the render function being called and the displaying of elements on the screen. This entire process is called reconciliation.

### Q2: What are the differences between a class component and functional component?
> Difficulty: ⭐⭐

* **Class component or statefull component:** allows you to use additional features such as local state and lifecycle hooks.
* **Functional component or stateless component:** Your component just receives props and renders them to the page.

### Q3: What are refs used for in React?
> Difficulty: ⭐⭐

*Refs* are an escape hatch which allow you to get direct access to a DOM element or an instance of a component. 

### Q4: Describe how events are handled in React.
> Difficulty: ⭐⭐

In order to solve cross browser compatibility issues, your event handlers in React will be passed instances of SyntheticEvent, which is React’s cross-browser wrapper around the browser’s native event. These synthetic events have the same interface as native events you’re used to, except they work identically across all browsers. React will listen to all events at the top level using a single event listener. This is good for performance and it also means that React doesn’t need to worry about keeping track of event listeners when updating the DOM.

### Q5: What are the differences between state and props?
> Difficulty: ⭐⭐

* *Props* get passed to component as read-only data and similar to function parameters
* *State* is managed by component and can changed at any time with `setState()` method

### Q6: How to create refs ?
> Difficulty: ⭐⭐

There are two ways to create refs in React:
* *Refs* are created by using `React.createRef()` method
* And: 
```javascript
    class UserForm extends Component {
        render (){
            return (
            <form onSubmit={this.handleSubmit}>
                <input
                type='text'
                ref={(input) => this.input = input} />
                <button type='submit'>Submit</button>
            </form>
        }
    } 
```

### Q7: What are Higher-Order components?
> Difficulty: ⭐⭐

**A higher-order component (HOC)** is a function that takes a component and returns a new component.

### Q8: What is the purpose of using super constructor with props argument?
> Difficulty: ⭐⭐

A child class constructor cannot make use of `this` reference until `super()` method has been called. The same applies for ES6 sub-classes as well. The main reason of passing props parameter to `super(`) call is to access `this.props` in your child constructors.


### Q9: What are controlled components?
> Difficulty: ⭐⭐⭐

In HTML, form elements such as `<input>, <textarea>, and <select>` typically maintain their own state and update it based on user input. When a user submits a form the values from the aforementioned elements are sent with the form. With React it works differently. The component containing the form will keep track of the value of the input in it's state and will re-render the component each time the callback function e.g. `onChange` is fired as the state will be updated. An input form element whose value is controlled by React in this way is called a **controlled component**.

### Q10: What is equivalent of the following using React.createElement?
> Difficulty: ⭐⭐⭐

**Question:**
```javascript
const element = (
  <h1 className="greeting">
    Hello, world!
  </h1>
);
```

**Answer:**
```javascript
React.createElement(
    'h1',
    {className: 'greeting'},
    'Hello, World!'
);
```

### Q11: What is JSX?
> Difficulty: ⭐⭐⭐

When Facebook first released React to the world, they also introduced a new dialect of JavaScript called JSX that embeds raw HTML templates inside JavaScript code. JSX code by itself cannot be read by the browser; it must be transpiled into traditional JavaScript using tools like Babel and webpack.

### Q12: Why should not we update the state directly?
> Difficulty: ⭐⭐⭐

If you try to update state directly then it won’t re-render the component. Instead use `setState()` method. It schedules an update to a component’s state object. When state changes, the component responds by re-rendering

### Q13: What are the different phases of ReactJS component lifecycle?
> Difficulty: ⭐⭐⭐

There are four different phases of React component’s lifecycle:
1. **Initialization**: In this phase react component prepares setting up the initial state and default props.
2. **Mounting**: The react component is ready to mount in the browser DOM. This phase covers `componentWillMount` and `componentDidMount` lifecycle methods.
3. **Updating**: In this phase, the component get updated in two ways, sending the new props and updating the state. This phase covers `shouldComponentUpdate`, `componentWillUpdate` and `componentDidUpdate` lifecycle methods.
4. **Unmounting**: In this last phase, the component is not needed and get unmounted from the browser DOM. This phase include `componentWillUnmount` lifecycle method.

### Q14: What are the lifecycle methods of ReactJS?
> Difficulty: ⭐⭐⭐

* **componentWillMount**: Executed before rendering and is used for App level configuration in your root component.
* **componentDidMount**: Executed after first rendering and here all AJAX requests, DOM or state updates, and set up eventListeners should occur.
* **componentWillReceiveProps**: Executed when particular prop updates to trigger state transitions. (**Note**: UNSAFE method)
* **shouldComponentUpdate**: Determines if the component will be updated or not. By default it returns true. If you are sure that the component doesn't need to render after state or props are updated, you can return false value. It is a great place to improve performance as it allows you to prevent a rerender if component receives new prop.
* **componentWillUpdate**: Executed before re-rendering the component when there are pros & state changes confirmed by shouldComponentUpdate which returns true.
* **componentDidUpdate**: Mostly it is used to update the DOM in response to prop or state changes.
* **componentWillUnmount**: It will be used to cancel any outgoing network requests, or remove all event listeners associated with the component.

### Q15: What are advantages of using React Hooks?
> Difficulty: ⭐⭐⭐

Primarily, hooks in general enable the extraction and reuse of stateful logic that is common across multiple components without the burden of higher order components or render props. Hooks allow to easily manipulate the state of our functional component without needing to convert them into class components. 

Hooks don’t work inside classes (because they let you use React without classes). By using them, we can totally avoid using lifecycle methods, such as `componentDidMount, componentDidUpdate, componentWillUnmount`. Instead, we will use built-in hooks like `useEffect`.

### Q16: What are React Hooks?
> Difficulty: ⭐⭐⭐

**Hooks** are a new addition in React 16.8. They let you use state and other React features without writing a class. With Hooks, you can extract stateful logic from a component so it can be tested independently and reused. Hooks allow you to reuse stateful logic without changing your component hierarchy.

### Q17: What is useState() in React?
> Difficulty: ⭐⭐⭐

**Example:**
```javascript
    const [counter, setCounter] = useState(0);
```
`useState` is one of build-in react hooks. `useState(0)` returns a tuple where the first parameter `count` is the current state of the counter and `setCounter` is the method that will allow us to update the counter's state.

### Q18: What is StrictMode in React?
> Difficulty: ⭐⭐⭐

React's StrictMode is sort of a helper component that will help you write better react components, you can wrap a set of components with `<StrictMode />` and it'll basically:
* Verify that the components inside are following some of the recommended practices and warn you if not in the console.
* Verify the deprecated methods are not being used, and if they're used strict mode will warn you in the console.
* Help you prevent some side effects by identifying potential risks.

### Q19: Why do class methods need to be bound to a class instance?
> Difficulty: ⭐⭐⭐

In JavaScript, the value of `this` changes depending on the current context. Within React class component methods, developers normally expect this to refer to the current instance of a component, so it is necessary to bind these methods to the instance.

### Q20: What is prop drilling and how can you avoid it?
> Difficulty: ⭐⭐⭐

When building a React application, there is often the need for a deeply nested component to use data provided by another component that is much higher in the hierarchy. The simplest approach is to simply pass a prop from each component to the next in the hierarchy from the source component to the deeply nested component. This is called **prop drilling**.

The primary disadvantage of prop drilling is that components that should not otherwise be aware of the data become unnecessarily complicated and are harder to maintain.

To avoid **prop drilling**, consider to use **Redux** or **React context**.

### Q21: Describe Flux vs MVC?
> Difficulty: ⭐⭐⭐⭐

Traditional MVC patterns have worked well for separating the concerns of data (Model), UI (View) and logic (Controller) — but MVC architectures frequently encounter two main problems:

* **Poorly defined data flow**: The cascading updates which occur across views often lead to a tangled web of events which is difficult to debug.
* **Lack of data integrity**: Model data can be mutated from anywhere, yielding unpredictable results across the UI.

With the Flux pattern complex UIs no longer suffer from cascading updates; any given React component will be able to reconstruct its state based on the data provided by the store. The Flux pattern also enforces data integrity by restricting direct access to the shared data.

### Q22: What is the difference between a controlled component and an uncontrolled component?
> Difficulty: ⭐⭐⭐⭐

* **A controlled component** is a component where React is in control and is the single source of truth for the form data.
* **An uncontrolled component** is where your form data is handled by the DOM, instead of inside your React component.

### Q23: What is the React context?
> Difficulty: ⭐⭐⭐

It's an experimental API that allows you to pass data down through a tree of components without having to use props.

### Q24: How to apply validation on Props in ReactJS?
> Difficulty: ⭐⭐⭐⭐

When the application is running in development mode, React will automatically check for all props that we set on components to make sure they must right correct and right data type. For incorrect type, it will generate warning messages in the console for development mode whereas it is disabled in production mode due performance impact. The mandatory prop is defined with `isRequired`.

The set of predefined prop types are below

* `React.PropTypes.string`
* `React.PropTypes.number`
* `React.PropTypes.func`
* `React.PropTypes.node`
* `React.PropTypes.bool`

### Q25: How does React renderer work exactly when we call setState?
> Difficulty: ⭐⭐⭐⭐⭐

There are two steps of what we may call `render`:

1. Virtual DOM render: when `render` method is called it returns a new virtual dom structure of the component. This `render` method is called always when you call `setState()`, because `shouldComponentUpdate` always returns true by default. So, by default, there is no optimization here in React.

2. Native DOM render: React changes real DOM nodes in your browser only if they were changed in the Virtual DOM and as little as needed - this is that great React's feature which optimizes real DOM mutation and makes React fast.