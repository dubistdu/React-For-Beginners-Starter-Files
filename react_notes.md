# Golden rule of React - DON'T TOUCH THE DOM
means... don't randomly select element by doing things like...getElementBy

# Props
### Passing Dynamic data with props

Props are like attributes in html tag ex) type is not called attribute anymore. It's called props/
State is where data lives and props is how data gets somewhere where it needs to be displayed
there is no existing prop. You make yours own up
prop is like argument you pass to function
chrome dev tool
go console and type $0 it will show you what you clicked type $r it will show everything that component has so... $r displays what this is this as in like this.props

# Stateless Functional Components
If your component only has render method - just renders our some html - no need for a full blown React component
no need to make reusable component with class Something extends Reac...blah blah
there is no this in function (?!) . Only props gets passed down to
```
class Header extends React.Component {
  render() {
    return (
      <header className="top">
        <h1>
          Catch of the day
        </h1>
        <h3 className="tagline">
          <span>{this.props.tagline}</span>
        </h3>
       </header>
     );
   }
   
 instead..... make a stateless function  
 
 function Header(props) {
  return (
    <header className="top">
      <h1>
        Catch of the day
      </h1>
      <h3 className="tagline">
        <span>{props.tagline}</span>
      </h3>
     </header>
   );
 }
 
 change this to ES6
 
 const Header = (props) => {
 
  <header className="top">
    <h1>
      Catch of the day
    </h1>
    <h3 className="tagline">
      <span>{props.tagline}</span>
    </h3>
  </header>
 }
 ```
# helper
`import {helperName } from "../path";`

for importing helper functions...

# handling events in React
In react it wraps js event in synthetic event so it works across devices

`<button onClick={this.handleClick}>Click me!</button>` You just provide event name.
You don't do `this.handleClick()` like in js beause `()` will make event load on page load. Which means will run when component is mounted on page load/

After writing event, then go above return and then add/create handleClick function
```
handleClick() {
  alert("Hey!");
}
// onlclick, handleClick happens.
```
Everytime handling event gets confusing...just watch this https://courses.wesbos.com/account/access/592dd6fec373d435bb82dc0f/view/257751801

### handling input with ref
https://courses.wesbos.com/account/access/592dd6fec373d435bb82dc0f/view/257751801
1. `ref` (this actually touches the DOM) `createRef`  usage:`myInput = React.createRef();`
- custom method that's created by user (one that did not come with React.Compnent) needs to be bound to React
hence.... `bind`

```
import React from "react";
import { getFunName } from "../helpers";

class StorePicker extends React.Component {
  myInput = React.createRef();
 //   ^^^ input text
 
  goToStore = event => {
    // 1. Stop the form from submitting
    event.preventDefault();
    // 2. get the text from that input
    console.log(this);
    // 3. Change the page to /store/whatever-they-entered
  };
  // ^^^ explanation .... goToStore is a property just like myInput is a property of storePicker then we set it to an arrow //   // function which will allow us to to bind value of "this" (like this in console.log) to the storePicker component
  // in other words, it's binding goToStore method, which is a custom method to "StorePciker" component so we can use it.

  render() {
    return (
      <form className="store-selector" onSubmit={this.goToStore}>
        <h2>Please Enter A Store</h2>
        <input
          type="text"
          ref={this.myInput}
          required
          placeholder="Store Name"
          defaultValue={getFunName()}
        />
        <button type="submit">Visit Store →</button>
      </form>
    );
  }
}

export default StorePicker;
```
## Constructor (it's like an initializer in Ruby)

"The constructor method is a special method for creating and initializing an object created with a class. There can only be one special method with the name "constructor" in a class. A SyntaxError will be thrown if the class contains more than one occurrence of a constructor method.

A constructor can use the super keyword to call the constructor of the super class."
If you are using `constructor`, you always call `super`
When you call `super()`, this calls React.Component which needs to be ran before extending class Created ex) `StorePciker`

# state
* Where data lives
* form inputs video (video 14) good reference for form
    https://courses.wesbos.com/account/access/592dd6fec373d435bb82dc0f/view/257752755
    source code 
    https://github.com/wesbos/React-For-Beginners-Starter-Files/blob/master/stepped-solutions/14/components/AddFishForm.js
 * const (variable in soure code )  
    Constants are block-scoped, much like variables defined using the let statement. The value of a constant cannot change         through re-assignment, and it can't be redeclared.
    
    
   
