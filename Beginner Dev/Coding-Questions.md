# Full Stack Coding Questions

## Backend

### Return the sum of two numbers from the server (Use VS Code + Rest Client extension)

```Javascript
import express from 'express';
const app = express();
const PORT = 3000;
// middleware to parse JSON
app.use(express.json());
app.post('/sum', (req, res) => {
  const { a, b } = req.body;
  res.json({
    sum: a + b
  });
});
app.listen(PORT, () => {
  console.log(`Server running at http://localhost:${PORT}`);
});

```

```.http
POST http://localhost:3000/sum
Content-Type: application/json

{
  "a": 5,
  "b": 10
}

```

## Frontend

### Basic Counter App (React + Hooks)
Make it run here: https://nextleap.app/online-compiler/reactjs-programming

```
import React, { useState } from "react";

function Counter() {
  const [count, setCount] = useState(0);
  return (
    <div>
      <p>Count: {count}</p>
      <button onClick={() => setCount(count + 1)}>Increment</button>
    </div>
  );
}

export default Counter;

```

 ### Fetch and Display Users (React + useEffect)

```
import React, { useState, useEffect } from "react";

function UserList() {
  const [users, setUsers] = useState([]);
  const [loading, setLoading] = useState(true);

  useEffect(() => {
    fetch("https://jsonplaceholder.typicode.com/users")
      .then(response => response.json())
      .then(data => {
        setUsers(data);
        setLoading(false);
      });
  }, []);

  if (loading) return <div>Loading...</div>;
  return (
    <ul>
      {users.map(user => <li key={user.id}>{user.name}</li>)}
    </ul>
  );
}

export default UserList;

```
 ### Toggle Button (Dark mode to Light Mode)

```
import {useState} from "react"
export default function App() {
    const [mode, setMode] = useState("light")
    const changeMode = () => {
        mode==="light"?setMode("dark"):setMode("light");
    }
    const styles = {
        backgroundColor : mode === "light"?"white":"black",
        display: "flex",
        height: "100vh",
        alignItems:"center",
        justifyContent:"center"
        
    }
  return (
      <div style = {styles}>
          <button onClick = {changeMode}>{mode==="light"?"Dark Mode":"Light Mode"}</button>
      </div>
  )
}

```

 ### Take Input + Reverse String + Check Palindrom
```
import {useState, useEffect} from "react";
export default function App (){
    const [name, setName] = useState("Ayush")
    const [isPalindrom, setIsPalindrom] = useState(false);
    useEffect(() => {checkPalindrom()}, [name])
    const reverse = () =>{
        let len = name.length - 1;
        let reversed = "";
        while (len >= 0) {
            reversed += name[len]
            len--;
        }
        setName(reversed)
    }
    const checkPalindrom = () =>{
       let start = 0;
        let end = name.length - 1;
        while (start < end){
            if (name[start].toLowerCase() !== name[end].toLowerCase()){
                setIsPalindrom(false);
                return;
            }
            start++;
            end--;
        }
        setIsPalindrom(true);
    }
    
    return <div>
        <h4 >Enter your Name</h4>
        <input type = "text" onChange = {(e)=>{setName(e.target.value)}}></input>
        <h1>Name:{name}</h1>
        <button onClick = {reverse}>Reverse Name</button>
        <h4>It {isPalindrom?"is":"is not"} a palindrom.</h4>
    </div>
}

```

 ### TO DO App 
```
import {useState} from "react"
export default function App() {
    const [toDos, setToDos] = useState([]);
    const [text, setText] = useState("");
  return (
      <div>
            <input 
                type = "text" 
                value = {text} 
                onChange= {(e) => setText(e.target.value)}
                placeholder = "write what would you do"> 
            </input>
          <button onClick = {()=>setToDos([...toDos, text])}>Create To Do</button>
          <ul>{toDos.map((item, index) => (<li>{item}</li>))}</ul>
      </div>
  )
}

```
 ### TO DO App (Fancy)
Try it Yourself: https://nextleap.app/online-compiler/reactjs-programming/4vzbcxrp7

App.js
``` 
import { useState } from "react";

export default function App() {
  const [text, setText] = useState("");
  const [toDos, setToDos] = useState([]);

  const deleteHandler = (deleteIndex) => {
    setToDos(toDos.filter((_, index) => index !== deleteIndex));
  };

  const submitHandler = (e) => {
    e.preventDefault();
    if (!text.trim()) return;
    setToDos([...toDos, text]);
    setText("");
  };

  return (
    <div>
      <h1>My To Dos 📝</h1>
      <form onSubmit={submitHandler}>
        <input
          value={text}
          type="text"
          onChange={(e) => setText(e.target.value)}
          placeholder="Enter a todo"
        />
        <button type="submit">➕ Add ToDo</button>
      </form>

      <ul class = "toDos">
        {toDos.map((value, index) => (
          <li key={index} class = "toDo">
            {value} {" "}
            <button onClick={() => deleteHandler(index)}>❌ Delete </button>
          </li>
        ))}
      </ul>
    </div>
  );
}

```
styles.css 
```
body {
    display: flex;
    justify-content: center;
  font-family: sans-serif;
}

h1 {
  font-size: 1.5rem;
    display: flex;
    justify-content: center;
}
.toDos{
    padding: 0;
}
.toDo{
    display: flex;
    justify-content: space-between;
    list-style: none;
    margin: 10px 0;
    border: 2px solid black;
    boder-radius:12px;
    padding: 8px;
}

```

 ### Anoying Stuff
 #### Styled Button (HTML+CSS) 
```
<button class="my-btn">Click Me!</button>
<style>
    .my-btn {
        background: #4CAF50;
        color: white;
        padding: 10px 20px;
        border: none;
        border-radius: 5px;
    }
    .my-btn:hover {
        background: #45a049;
    }
</style>
```

 #### Responsiveness
```
<div class="container">
    <div class="box">A</div>
    <div class="box">B</div>
</div>
<style>
    .container {
        display: flex;
        flex-wrap: wrap;
    }
    .box {
        flex: 1 1 100px;
        background: #ddd;
        margin: 10px;
        height: 100px;
        text-align: center;
        line-height: 100px;
    }
</style>
```
 #### Change Flex Direction (Tailwind)
```flex flex-col md:flex-row```
