# case-reducer

## Installation

```bash
$ npm install case-reducer --save
```

## Usage

```js
import caseReducer from "case-reducer"
import {
  REQUEST_USER,
  USER_RESPONSE
} from "actions/user"

const initialState = {
  isFetching: false,
  id: null,
  username: null
}

const cases = {
  [ REQUEST_USER ] (state) {
    return {
      ...state,
      isFetching: true
    }
  },

  [ USER_RESPONSE ] (state, data) {
    const { user } = data

    return {
      ...state,
      isFetching: false,
      ...user
    }
  }
}

export default caseReducer(initialState, cases)
```

---

## See also

[![Travi$ Scott - Don't Play ft. Big Sean, The 1975](http://i.imgur.com/AR6HOsm.png)](https://www.youtube.com/watch?v=iQhLccjeHYI)