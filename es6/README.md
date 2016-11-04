# ES6 5rabbits practices

## `this` Reference in callbacks/promises

Bad Example:
```
class Timer extends React.Component {
  componentDidMount() {
    let self = this;
    asyncWork.then(function(data) {
      self.setState( { duration: data.duration } );
    });
  }
}
```

Good Example:
```
class Timer extends React.Component {
  componentDidMount() {
    asyncWork.then(data => {
      this.setState( { duration: data.duration } );
    });
  }
}
```

