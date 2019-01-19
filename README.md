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
