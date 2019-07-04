# React Redux Thunk

## Cara install

```bash
npm i redux
npm i react-redux
npm i react-redux-thunk
```

## Apa saja yang penting pada redux
1. Provider
2. Reducer
3. Action
4. Store
5. Connect

## Membuat Provider dari `react-redux`
```javascript
import React from 'react';
import App from './App';
import * as serviceWorker from './serviceWorker';
import { Provider } from 'react-redux';
import Store from './Store';

ReactDOM.render(
    <Provider store= {Store} ><App /> </Provider>
    , document.getElementById('root'));

serviceWorker.unregister();
```
## Membuat Reducer
## Membuat Action
## Membuat Store
