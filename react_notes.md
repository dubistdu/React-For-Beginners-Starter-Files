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

`<button onClick={this.handleClick}>Click me!</button>` you don't do `this.handleClick()` like in js beause `()` will make event load on page load. Which means will run when component is mounted on page load/

After writing event, then go above return and then add/create handleClick function
```
handleClick() {
  alert("Hey!");
}
// onlclick, handleClick happens.
```
Everytime handling event gets confusing...just watch this https://courses.wesbos.com/account/access/592dd6fec373d435bb82dc0f/view/257751801

