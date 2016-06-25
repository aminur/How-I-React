# Syntax (pt 1)

The ES6 way:
```
class myComponent extends React.Component {
  //code in here
}
```

This makes good sense. My component builds on top of React Components, thereby extends what _they_ can do, with what _I_ want to do.

>Render is a **MUST** if you want anything printed out.

The render function returns HTML so let's add that in:
```
class myComponent extends React.Component {
  render() {
    return <h2>Learning How To React</h2>;
  }
}
```

>Render does not print until it's called.

Call render like this:

`ReactDOM.render(<myComponent />, document.getElementById('target'));`

Simple function call with parameters of 'my component that I want to render', 'container to attach component to'. 

>We're using React DOM. It can return HTML directly but we're returning our component.

For this to work though, of course you need your target to exist in the HTML.

`<div id="target"></div>`

#### Summary 1

>>The basics of React syntax. How to print something to the screen. Where you would normally type outright HTML, here the HTML is coming from your JavaScript - it is coming the way React wants you to 'render' your component. When you want to output HTML, think 'render'. Render needs to be defined, and called. The component needs a target in the HTML so it knows where to render.

#Syntax (pt 2)

You may want to putput multiple lines of HTML when rendering your component.

Update the code to include parenthese and a parent tag for _all_ the output:

```
class myComponent extends React.Component {
  render() {
    return (
      <div id='necessary-single-parent-container'>
        <h2>First line</h2>
        <h4>Second line which causes a parent container tag to be required</h4>
      </div>
    );
  }
}
```

>Only one parent HTML tag per component output

#### Summary 2

>>The basics of React syntax. How to print something to the screen. Where you would normally type outright HTML, here the HTML is coming from your JavaScript - it is coming the way React wants you to 'render' your component. When you want to output HTML, think 'render'. Render needs to be defined, and called. The component needs a target in the HTML so it knows where to render.
