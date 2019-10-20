# React Life Cycle

- Component Create Life Cycle 
```
constructor(props) -> getDerivedStateFromProps(props, state) -> 
componentWillMount() -> render() -> Render Child Components -> componentDidMount()
```

- Constructor 
```
constructor(props){
  super(props)
}
```

