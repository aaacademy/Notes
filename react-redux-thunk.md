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

Ada 3 hal penting yang dipakai dari `redux` untuk menjalankan **Store**
1. createStore, untuk menjadikan file menjadi `Store`
2. combineReducers, untuk menggabungkan beberapa reducer menjadi 1
3. applyMiddleware, sebagai perantara antara load dan selesai load data pada reducer

Pada kasus ini kita menggunakan `react-thunk` sebagai middleware untuk menjadikan mutable menjadi immutable pada API

```javascript
import {
  createStore,
  combineReducers, 
  applyMiddleware
} from 'redux'
import ReducerWeb from './Reducer/ReducerWeb'
import NewsReducer from './Reducer/NewsReducer'
import thunk from 'redux-thunk';

const combine = combineReducers({
  web: ReducerWeb,
  news: NewsReducer,
})

const Store = createStore( combine, applyMiddleware(thunk) )
export default Store
```
