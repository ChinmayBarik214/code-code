### ReactDOMServer.renderToString(<SeoComponent/>)

To load html before all jsx for search engines that are trying to index the content of your pages so people can find you.

```js
class App extends React.Component {
  constructor(props) {
    super(props);
  }
  render() {
    return <div/>
  }
};

// Change code below this line
ReactDOMServer.renderToString(<App/>)
```
