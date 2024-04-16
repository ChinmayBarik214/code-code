## The random parameters in Event listeners (event, element, etc.)
Each event listener needs to be added to listen for some DOM event (`onClick`, `onChange`, `onSubmit` etc. when added on HTML elements, and `onclick`, `onchange`, `onsubmit`, `keydown`, etc. when passed as event listener in `document.addEventListener, document.removeEventListener`, etc.) and trigger a callback function, i.e., the event handler, when this event occurs. These callback functions have some parameters depending on the event that triggers them.

For example in the following code, notice the keydown event listener being added. When the callback is specified we do so without any parameters, yet we are passing an argument (event) to it in it’s definition.
```js
class MyComponent extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      message: ''
    };
    this.handleEnter = this.handleEnter.bind(this);
    this.handleKeyPress = this.handleKeyPress.bind(this);
  }
  // Change code below this line
  componentDidMount() {
    document.addEventListener("keydown", this.handleKeyPress)
  }
  componentWillUnmount() {
    document.removeEventListener("keydown", this.handleKeyPress)
  }
  // Change code above this line
  handleEnter() {
    this.setState((state) => ({
      message: state.message + 'You pressed the enter key! '
    }));
  }
  handleKeyPress(event) {
    if (event.keyCode === 13) {
      this.handleEnter();
    }
  }
  render() {
    return (
      <div>
        <h1>{this.state.message}</h1>
      </div>
    );
  }
};
```
This is because the callback triggered by the `keydown` event has the `event` positional argument pre-defined, which can be used to specify which key will trigger the event handler using `event.keycode` method.

Therefore, it’s a good idea to lookup these pre-defined positional arguments for each event before creating them.

### Note
Always remember to remove an event listener (in the above example it’s done using `removeEventListener`) after it's event handler has been called or you'll end up with way too many event listeners active and listening at once.
