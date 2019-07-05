# React Component Lanjutan

## Composition
React `props.children`: Apapun yang bedada diantara component merupakan children

## Context
Digunakan jika :
- Ingin menurunkan `props` berlanjut agar component tidak terasa kotor jika diturunin, kemudian diturunin kembali
- Bila memberi nilai dengan hubungan bukan parent-child

### Cara membuat contex

```javascript
import React, { Component } from 'react'

const MyContext = React.createContext()

class App extends Component {
  render() {
    return (
      <MyContext.Provider value="red">
        <Button />
      </MyContext.Provider>
    )
  }
}

class Button extends Component {
  render() {
    return (
      <MyContext.Consumer>
        { (nilaiTurunan) => (
          <button>Dengan nilai: {nilaiTurunan} </button>
        ) }
      </MyContext.Consumer>
    )
  }
}
```

Agar context dapat dipanggil dimanapun seperti lifecycle gunakan kode berikut
```javascript
class Button extends Component {
  static contextType = MyContext
  render() {
    let value = this.context
    return (
      <button>Dengan nilai: {value} </button>
    )
  }
}
```

## Hoc - High Order Component
Merupakan fungsi yang merender component dan penggunaannya pada export namaFungsi(App)


