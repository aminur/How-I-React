#Data

To add data into the component, let's start by using JSX attributes. Normal XML syntax here for attributes being passed as part of the component.
```
ReactDOM.render(<myComponent key="value" number={ //JScript in here } />, document.getElementbyId('target'));
```
**NB: The above code will fail, as JSX attributes are not permitted to be empty**

Let's fix and format the above to make it clearer:
```
ReactDOM.render(
  <myComponent keyx="value" number={4} />,
  document.getElementbyId('target')
);
```
**NB: `key` and `ref` are reserved keywords so you cannot use them as keys in your data (JSX attributes)**

We can see that hardcoding a string is simple but to pass a number with a data type, it has to come from Javascript.

>Data is passed as key-value pairs, but if the value is a number or dynamic, it must be from Javascript - passed using curly braces {}

All the data is on the component in this case, so let's add a console.log:
```
class myComponent extends React.Component {
  render() {
    console.log(this); // <---- Log the component properties
    return (
      <div>Testing JSX attributes</div>
    );
  }
}
```

You'll see from the output that the data was passed to `props` as an Object.
```
props: Object
  keyx: "value"
  number: 4
```

>You can drill down, in console.log, into properties e.g. `console.log(this.props.keyx)`

By now you would realise 'props' stands for properties. You should also realise that within your HTML in the render function, you access the values like so e.g. to get 'number':
```
class myComponent extends React.Component {
  render() {
    
    return (
      <div className="cannot-use-class-as-it-is-a-keyword-in-React-for-React-classes">
        {this.props.number}
      </div> //Outputs 4
    );
  }
}
```
Did you notice something extra in the above code?

**NB: Remember to use `className` instead of `class` (for CSS purposes etc.) on JSX HTML**

#### Summary
JSX attributes help to easily add data to the component and the syntax resembles XML attributes, aside from JavaScript being contained in curly braces {}. HTML styling should be done using the `className` attribute, **NOT `class`**
