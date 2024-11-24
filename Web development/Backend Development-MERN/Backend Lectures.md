
#### Lecture 1 : Create a Backend Project.

==`Step 1`== Initiate a node package

```jsx
npm init
```

==`Step 2`== Create a entry point `( index.js )` and add a custom script to start the package `npm run start`

==`Step 3`== Install express.js

```jsx
npm install express
```

==`Step 4`== Create a simplet express app in index.js

```jsx
const express = require('express')         // imports express
const app = express()                  // create an app object from express class
const port = 3000                      // desired port for the project

app.get('/', (req, res) => {            // creating response
  res.send('Hello World!')
})

app.listen(port, () => {
  console.log(`Example app listening on port ${port}`)         // port listen
})

```

==`Step 5`== Create .env files

```jsx
install dotenv package
include required packages : require('dotenv').config()

create a .env file and write all environmental variable there.
access env var:  console.log(process.env.VAR_NAME)

```

#### Lecture 2 : Connect Frontend and Backend

##### Backend

```jsx
// const express = require('express')
import express from "express"
import 'dotenv/config'   // setup .env file

const app = express()

app.get('/', (req , res) => {
    res.send("Server is ready")
})

// setting proxy 
app.get('/api/jokes' , (req , res) => {
    // array of 5 jokes wiht id , title and body.
    const jokes = [
        {
            id : 1,
            title : "Joke 1",
            body : "Joke 1 body"
        },
        {
            id : 2,
            title : "Joke 2",
            body : "Joke 2 body"    
        },
        {
            id : 3,
            title : "Joke 3",
            body : "Joke 3 body"    
        },
        {
            id : 4,
            title : "Joke 4",
            body : "Joke 4 body"    
        },
        {
            id : 5,
            title : "Joke 5",
            body : "Joke 5 body"
        }
       
    ]
    res.send(jokes)
})

const port = process.env.PORT || 3000;

app.listen(port, () => {
    console.log(`server at <http://localhost>:${port}`);
})
```
##### Frontend

```jsx
import { useEffect, useState } from "react";
import "./App.css";
import axios from "axios";

function App() {
	const [jokes, setJokes] = useState([]);
	
	
	// fetching data using axios.
	useEffect(() => {
		axios
			.get("/api/jokes")   // proxy configure in vite.config.js
			.then((res) => {
				setJokes(res.data);
				console.log(res.data);
			})
			.catch((err) => {
				console.log("error axios data: ", err);
			});
	}, []);

	return (
		<>
			<h1>Learning backend with Hitesh Sir</h1>
			<p>Jokes : {jokes.length}</p>
			{jokes.map((joke) => (
				<div key={joke.id}>
					<h3>{joke.title}</h3>
					<p>{joke.body}</p>
				</div>
			))}
		</>
	);
}

export default App;

```

Adding a proxy will fix CORS error:
```jsx
// vite.config.js

import { defineConfig } from 'vite'
import react from '@vitejs/plugin-react'

// <https://vite.dev/config/>
export default defineConfig({
  plugins: [react()],
  server: {
    proxy: {
      '/api' : "http://localhost:3000"
    }
  }
})

```
#### Lecture 3 : Mongoose Data Modelling
##### Make visual data modelling of how to store the data.
![[Assets/model1.png]]
![[Assets/model2.png]]

##### Creating data modeling using mongoose.



### Lecture 4 


### Lecture 5

### Lecture 6

### Lecture 7


