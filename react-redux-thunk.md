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
```javascript
const initState = {
  warna : 'red',
  loading : true
}

export default (state = initState, action) => {
  switch (action.type){
    case 'GETWARNA': 
      return { 
        ...state,loading:false
      }
    default:
      return state
  }
}
```

```javascript
const initialState = {
  news: [],
  isLoaded: false
}

export default (state = initialState, action) => {
  switch (action.type) {
    case 'GET_NEWS_REQUEST':
      return {
        ...state,
        isLoaded: true
      }
    case 'GET_NEWS_DONE':
      return {
        ...state,
        news: action.payload.news,
        isLoaded: false
      }
    case 'GET_NEWS_ERROR':
      return {
        ...state
      }
    default:
      return state
  }
}
```
## Membuat Action
```javascript
import axios from 'axios'
import { key, URL_News } from '../secret'
export const getNews = (keyword) => {
  return dispatch => {
    dispatch({
      type: 'GET_NEWS_REQUEST'
    })
    axios({
      method: 'GET',
      url: URL_News + `everything?q=${keyword}&from=2019-02-07&sortBy=publishedAt&apiKey=${key}`
    })
      .then((response) => {
        dispatch({
          type: 'GET_NEWS_DONE',
          payload: {
            news: response.data.articles
          }
        })
      })
      .catch(err => {
        dispatch({
          type: 'GET_NEWS_ERROR'
        })
      })
  }
}
```
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

## Membuat Connect
```javascript
import React, { Component } from 'react';
import {connect} from 'react-redux'
import CardNews from '../Component/CardNews'
import {getNews } from '../Store/Action/NewsAction'
import Loading from '../Component/Loading'

class News extends Component {
  componentDidMount(){
    this.props.NewsAction('technology')
  }

  render() {
    return (
      <div className="row">
        {
          this.props.news.news.length > 0 ? (
            this.props.news.news.map((list, i)=>(
              <div className="col-md-6">
              <CardNews key={i} berita={list} />
              </div>
            ))
          ) : (<Loading />)
        }
      </div>
    )
  }
}

const mapStateToProps = (Store) => {
    return {
        news:Store.news
    }
}

const mapDispatchToProps = dispatch => {
  return {
    NewsAction: (data) => {
      dispatch(getNews(data))
    }
  }
}

export default connect(mapStateToProps,mapDispatchToProps)(News);
```
