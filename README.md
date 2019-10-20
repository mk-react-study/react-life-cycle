# React Life Cycle

- Note- Update state withing life cycle hooks can create infinit loop.
### Component Create Life Cycle 
```
constructor(props) -> getDerivedStateFromProps(props, state) -> 
componentWillMount() -> render() -> Render Child Components -> componentDidMount()
```
### Props Update Lifecycle
```
getDerivedStateFromProps(props, state) -> shouldComponentUpdate(nextProps,nextState)
-> render() -> Update Child Component Props -> getSnapshotBeforeUpdate(prevProps, prevState)
-> componentDidUpdate()
```

### useEffect

- This is hook so can be use with functional component.
- This can be consider as combination of componentDidMount and componentDidUpdate
- This can be use multiple time, can put different conditions.
- Version one this will execute only one time because of [] pass in condition.
  * 1st time when component attach and remove
```
useEffect(() => {
    console.log('[Cockpit.js] useEffect');
    // Http request...
    setTimeout(() => {
      alert('Saved data to cloud!');
    }, 1000);
    return () => {
      console.log('[Cockpit.js] cleanup work in useEffect');
    };
  }, []);
```
- Version 2 
```
useEffect(() => {
  console.log('[Cockpit.js] 2nd useEffect');
  return () => {
    console.log('[Cockpit.js] cleanup work in 2nd useEffect');
  };
});
```
- Constructor 
```
constructor(props){
  super(props)
}
```

