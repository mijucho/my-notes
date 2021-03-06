# my-notes
my notes

## Week 1 
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/reverse

How to reverse arrays

```
const a = [1, 2, 3];

console.log(a); // [1, 2, 3]

a.reverse();

console.log(a); // [3, 2, 1]

```

--------

## Week 2

How to take the ID from a URL request and find an object inside an array with a matching ID
```
server.get('/locations/:id', (req, res) => {
 const id = req.params.id
  for(i = 0; i < data.length; i++){
    if (data[i].id == id){
      res.render('home',data[i])
    }
  }
  
})
```
--------- or 
```

server.get('/person/:id', (req, res) => {
  var person = people.find(person => person.id == req.params.id)
  if(!person) {
    res.send('not found')
} else {
  res.render('person', person)
}

})
```
## week4 React
------ Intro code----
App.jsx
```
import React from 'react'
import Monkeys from './Monkeys'

const monkeys = ['sam','tim','bob']
const App = () => {
  return (
    <
    div>
      <h1>Zoo!!</h1>
      <Monkeys names ={monkeys} />
    </div>
  )
}
export default App
```
Monkeys.jsx
```
import React from 'react';

function Monkeys({names}) {

    return <div>
        <ul>
        {names.map((monkey,i) => <li key ={i}>{monkey}</li>)}
        </ul>
    </div>
}

export default Monkeys
```
Result---
- Zoo!!
- sam
- tim
- bob
------
Converting a Function to a Class & state
```
import React from 'react'
import Monkeys from './Monkeys'

const monkey = ['Sam','Tim', 'Bob']

class App extends React.Component {
  constructor(props) {
    super(props)
    this.state ={
      showMonkeys:false
      
  }
}
render() {
 return (
    < div>
      <h1>Zoo!!</h1>
   {this.state.showMonkeys ? <Monkeys names ={monkey} /> : ''} 
    </div>
  )
}
}

export default App
```
result
- Zoo!!
------
onClick evnt
```
import React from 'react'
import Monkeys from './Monkeys'

const monkey = ['Sam','Tim', 'Bob']

class App extends React.Component {
  constructor(props) {
    super(props)
    this.state ={
      showMonkeys:false,
      title:'Hi Anmals'
  }
}
render() {
  const {title, showMonkeys} = this.state

 return (
    < div>
      <h1>{title}!!</h1>
      <button onClick={() => this.setState({showMonkeys:true})}>Toggle</button>
      {showMonkeys ? <Monkeys names ={monkey} /> : ''} 
    </div>
  )
}
}

export default App
```
result---
- Hi Anmals!!
- Toggle
- Sam
- Tim
- Bob
 result changed ---
- Hi Anmals!!
- Toggle
----
proper Toggle Function
```
 return (
    < div>
      <h1>{title}!!</h1>
      <button onClick={() => this.setState({showMonkeys: !showMonkeys})}>Toggle</button>
      {showMonkeys ? <Monkeys names ={monkey} /> : ''} 
    </div>
  )
}
}

export default App
```
-----
Toggle evnt with clean code
```
render() {
  const {title, showMonkeys} = this.state
  const toggle = () => this.setState({showMonkeys: !showMonkeys})

 return (
    < div>
      <h1>{title}!!</h1>
      <button onClick={toggle}>Toggle</button>
      {showMonkeys ? <Monkeys names ={monkey} /> : ''} 
    </div>
  )
}
}

export default App
```
----
Advance JS with function out of context need 'bind(this)'
```
render() {
  const {title, showMonkeys} = this.state
  let toggle = function() {
    this.setState({showMonkeys: !showMonkeys})
  } 
    toggle =toggle.bind(this)  

 return (
    < div>
      <h1>{title}!!</h1>
      <button onClick={toggle}>Toggle</button>
      {showMonkeys ? <Monkeys names ={monkey} /> : ''} 
    </div>
  )
}
}
export default App
```
-------
evt.preventDefault()
```
import React from 'react'
import Monkeys from './Monkeys'

const monkey = ['Sam','Tim', 'Bob']

function clickLink(evt) {
  console.log('clicked')
  evt.preventDefault()
}

class App extends React.Component {
  constructor(props) {
    super(props)
    this.state ={
      showMonkeys:true,
      title:'Hi Anmals'
  }
}
toggle (evt) {
  this.setState({showMonkeys: !this.state.showMonkeys})
}
render() {
  const {title, showMonkeys} = this.state
 return (
    < div>
      <h1>{title}!!</h1>
      <a href='/404' onClick={clickLink}>Freedom</a>
       <button onClick={this.toggle.bind(this)}>Toggle</button>
      {showMonkeys ? <Monkeys names ={monkey} /> : ''} 
    </div>
  )
}
}

export default App
```

