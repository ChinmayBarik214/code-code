## Event handler vs listener
Event handlers are sometimes called event listeners — they are pretty much interchangeable for our purposes, although
strictly speaking, they work together. The listener listens out for the event
happening, and the handler is the code that is run in response to it happening.

### Syntax
Event listeners start with `on` eg. onsubmit and event handlers are functions that these event listeners call.
```html
<!DOCTYPE html>
<html>

<body>

  <p>When you submit the form, a function is triggered which alerts some text.</p>

  <form action="/action_page.php" onsubmit="myFunction()">
    Enter name: <input type="text" name="fname">
    <input type="submit" value="Submit">
  </form>

  <script>
    function myFunction() {
      alert("The form was submitted");
    }
  </script>

</body>

</html>
```
### Note
In JSX event listeners start with `on` and are followed by a capital letter due to HTML attributes being written in
camelCase, not doing so is a common source of error, i.e., `onsubmit` becomes `onSubmit`.
