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
---------------
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
---
