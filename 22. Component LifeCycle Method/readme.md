# Component Lifecycle Methods

> You can think of React lifecycle methods as the series of events that happen from the birth of a React component to its death.

- Not exists in `functional` components.
- `useEffect` - hook works almost the same.


|Lifecycle Phases|Methods|Description|  
|---|---|---|
|Mounting|`constructor`,`static getDerivedStatefromProps`,`render` & `componentDidMount`|When an instance of a component is being `created` & `inserted` into the `DOM`| 
|Updating|`static getDerivedStatefromProps`, `shouldComponentUpdate`, `render`, `getSnapshotBeforeUpdate` & `componentDidUpdate`|When a component is being  re-rendered as a result of changes to either its props or state|   
|Unmounting|`componentWillUnMount`|When a component is being removed from the `DOM`|
|Error|`static getDerivedStatefromError` & `componentDidCatch`|When there is an error during rendering of a life-cycle method or in the constructor of any child component |