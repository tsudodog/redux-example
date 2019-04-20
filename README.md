# Redux Notes
[Redux 2019 Simple guide](https://www.valentinog.com/blog/redux/)
## Main Redux Concepts
The redux store is like a brain for redux, it is in charge for handling all the moving parts within Redux

The state of the application lives as a single, immutable object within the store.

Whent he store recieves an action it triggers a reducer which returns the next state. 


## The Reducer
Reducers take two parameters the state and action. Reducers typically are comprised of a switch statement, however the 2019 guide prefers if statements (this is largely convention based and preferenctial I think).

"The reducer calculates the next state depending on the action type. Moreover, it should return at least the initial state when no action type matches."

This is an anti pattern that breaks the key principals of react reducers, namely functional purity.

```javascript
// src/js/reducers/index.js
import { ADD_ARTICLE } from "../constants/action-types";
const initialState = {
  articles: []
};
function rootReducer(state = initialState, action) {
  if (action.type === ADD_ARTICLE) {
    state.articles.push(action.payload);
  }
  return state;
}
export default rootReducer;
```


