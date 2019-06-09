# ReactJS-Lifecycle-Methods

___

## Mounting Cycle

`componentWillMount()`

This method is invoked only once, before rendering occurs for the first time. At this point, there is still no native UI rendered for this element.


`componentDidMount()`

This method is invoked only once, after rendering occurs for the first time. At this point, the native UI for this element has finished rendering, and may be accessed through `this.refs` for direct manipulation. If you need to make async API calls or execute delayed code with `setTimeout()`, that should generally be done in this method.

___

## Updating Cycle

`componentWillReceiveProps()`

The parent of this component has passed a new set of `props`. This component will re-render. You may optionally call `this.setState()` to update this component's internal state before the `render()` method is called.

`shouldComponentUpdate()`

Based on the next values of `props` and `state`, a component may decide to re-render or not to re-render. The base class's implementation of this method always returns `true` (the component should re-render). For optimization, override this method and check if either `props` or `state` have been modified, e.g. run an equality test of each key/value in these objects. Returning `false` will prevent the `render()` method from being called.

`componentWillUpdate()`

This method is invoked, after the decision has been made to re-render. You may not call `this.setState()` here, since an update is already in progress.

`componentDidUpdate()`

This method is invoked after re-rendering occurs. At this point, the native UI for this component has been updated to reflect the React Element returned from the `render()` method.

`componentWillUnmount()`


