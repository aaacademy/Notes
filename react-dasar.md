# React Dasar

Kalau kata facebook sih, react itu hanaya library kecil yang membantu menghilangkan rasa sakit saat membangun UI pada web atau mobile.

Pada React sendiri memiliki beberapa hal dasar yang harus dipahami:
1. Comoponent
2. Props
3. State
4. Lifecycle

## Component
Component dalam react dapat dibuat dengan 2 cara, yatu dengan membuat class atau dengan membuat function. Tapi apa bedanya class dengan function pasti memiliki kelebihan masing-masing.

1. Dengan class

```javascript
import React, { Component } from 'react'

class App extends Component {
  constructor(props) {
    super(props)
    this.state = {
      name: '',
    }
  }
  
  render() {
    return (
      <div>Wellcome Asrul</div>
    )
  }
}

export default App
```

2. Dengan function

```javascript
import React, { Component } from 'react'

const Hello = ({ name }) => (<div>Hello, {name}!</div>);

export default Hello
```

Lantas bagai mana cara mengaksesnya?
Okay, cara mengakses komponent adalah dengan menjaikannya sebagai tag HTML, contoh component Hello akan diakses menjadi `<Hello />`

## Props
Props adalah cara komponent mengoper data ang berasal dari parent ke child dengan kata lain garis lurus kebawah.

```javascript
<Hello name="Asrul">
```
Dari component diatas misal sebuah komponent yang berisi komponent `Hello`, maka itu akan menurunkan data pada component `Hello` dengan props dengan `key` **name** dan `value` **Asrul**

## State
## Lifecycle
