# :zap: MERN Full Stack Tracker

* Mongo Express React Node (MERN) full-stack app, integrates React frontend with Node.js backend.
* Note on full-stacks: MEAN stack a better option for large-scale applications while MERN stack leads the race in the faster development of smaller applications.
* Tutorial code from [From Scratch - Développement Web](https://www.youtube.com/channel/UCHGLV13U7YRbjrKpqfbtyYg) with changes to styling and logic - see [:clap: Inspiration](#clap-inspiration) below
* **Note:** to open web links in a new window use: _ctrl+click on link_

![GitHub repo size](https://img.shields.io/github/repo-size/AndrewJBateman/mern-stack-data?style=plastic)
![GitHub pull requests](https://img.shields.io/github/issues-pr/AndrewJBateman/mern-stack-data?style=plastic)
![GitHub Repo stars](https://img.shields.io/github/stars/AndrewJBateman/mern-stack-data?style=plastic)
![GitHub last commit](https://img.shields.io/github/last-commit/AndrewJBateman/mern-stack-data?style=plastic)

## :page_facing_up: Table of contents

* [:zap: MERN Stack Data](#zap-mern-stack-data)
  * [:page_facing_up: Table of contents](#page_facing_up-table-of-contents)
  * [:books: General info](#books-general-info)
    * [:books: Backend](#books-backend)
    * [:books: Frontend](#books-frontend)
  * [:camera: Screenshots](#camera-screenshots)
  * [:signal_strength: Backend Technologies](#signal_strength-backend-technologies)
  * [:signal_strength: Frontend Technologies](#signal_strength-frontend-technologies)
  * [:floppy_disk: Setup - Backend](#floppy_disk-setup---backend)
    * [:floppy_disk: Setup - Frontend](#floppy_disk-setup---frontend)
  * [:computer: Code Examples](#computer-code-examples)
  * [:cool: Backend Features](#cool-backend-features)
    * [:cool: Frontend Features](#cool-frontend-featurres)
  * [:clipboard: Status & ToDo List](#clipboard-status-and-todo-list)
  * [:clap: Inspiration](#clap-inspiration)
  * [:envelope: Contact](#envelope-contact)

## :books: General info

### :books: Backend

* MongoDB Atlas used as the backend database - requires mongodb to be running
* [Mongoose query models](https://mongoosejs.com/docs/queries.html) used to interact with the database
* Postman used to test the backend
* Note: I used 'my ip address' as the whitelist network access in MongoDB.Atlas but this required daily updating when my ip address changed - otherwise with a non-matching ip address the backend simply did not work. Better to use the localhost address to avoid this problem but may be less secure.
* Node.js routes used with controller functions
* ![Nodejs diagram](./img/diagram.png)

### :books: Frontend

* [React reducers](https://reactjs.org/docs/hooks-reference.html) functions that take the current state and an action as arguments, and return a new state result. In other words, (state, action) => newState.

## :camera: Screenshots

![Backend screenshot](./imgs/mongodb.png)
![Backend screenshot](./imgs/postman.png)

![Frontend screenshot](./imgs/list.png)

## :signal_strength: Backend Technologies

* [MongoDB Community Server v4](https://www.mongodb.com/download-center/community)
* [Mongoose v6](https://mongoosejs.com/) object modelling for Node.js
* [MongoDB Compass v1](https://www.mongodb.com/es/products/compass) to explore and manipulate MongoDB data
* [Express.js middleware v4](https://expressjs.com/)
* [Express Fileupload v1](https://www.npmjs.com/package/express-fileupload) to upload files
* [Node.js v14](https://nodejs.org/es/)
* [JSON Web Tokens - JWT v8](https://www.npmjs.com/package/jsonwebtoken) to supply JSON Web Tokens
* [bcrypt v5](https://www.npmjs.com/package/bcrypt) to hash passwords

## :signal_strength: Frontend Technologies

* [React framework v17](https://reactjs.org/)
* [Redux v4](https://www.npmjs.com/package/redux) state container for JavaScript apps.
* [Redux thunk v2](https://www.npmjs.com/package/redux-thunk) middleware
* [Font Awesome v5](https://fontawesome.com/) icon library & toolkit
* [Axios v0.21.4](https://www.npmjs.com/package/axios) promise-based http client

## :floppy_disk: Setup - Backend

* Install backend dependencies using `npm i`
* Install [nodemon](https://www.npmjs.com/package/nodemon) globally if you don't already have it
* Register with [MongoDB Atlas](www.mongodb.com), create & configure a database cluster and add username &  connection string to `config/.env` file
* Run `nodemon server` for a dev server
* Navigate to `http://localhost:5000/`. The server will automatically reload if you change any of the source files

### :floppy_disk: Setup - Frontend

* Change to `/client` directory run `npm start`. Frontend will open at `http://localhost:3000/`

## :computer: Code Examples

* React useReducer example with lazy state initialization by passing init function

```javascript
function init(initialCount) {
  return {count: initialCount};
}

function reducer(state, action) {
  switch (action.type) {
    case 'increment':
      return {count: state.count + 1};
    case 'decrement':
      return {count: state.count - 1};
    case 'reset':
      return init(action.payload);
    default:
      throw new Error();
  }
}

function Counter({initialCount}) {
  const [state, dispatch] = useReducer(reducer, initialCount, init);
  return (
    <>
      Count: {state.count}
      <button
        onClick={() => dispatch({type: 'reset', payload: initialCount})}>
        Reset
      </button>
      <button onClick={() => dispatch({type: 'decrement'})}>-</button>
      <button onClick={() => dispatch({type: 'increment'})}>+</button>
    </>
  );
}

```

## :cool: Backend Features

* All data stored in collections in a mongoDB Atlas database that costs nothing to use in the free tier option. Data can be edited from the mongoDB.Atlas collection or from React frontend

### :cool: Frontend Features

* Uses the [React componentDidMount() method](https://reactjs.org/docs/state-and-lifecycle.html)

## :clipboard: Status & To-Do List

* Status: Part working, requires more testing
* To-Do: Complete commenting etc. & test backend. Fix frontend. Replace all styling.

## :clap: Inspiration

* [Javascript Full-stack Projet MERN | Créer un réseau social | Partie Back-end](https://www.youtube.com/watch?v=SUPDFHuvhRc&list=PLEiMYEzpB4QsZIxBeWo9T1fCnii0XHfHP) - in French
* [Javascript Full-stack Projet MERN | Créer un réseau social | Partie Front-end](https://www.youtube.com/watch?v=ghdRD3pt8rg&list=PLEiMYEzpB4QsZIxBeWo9T1fCnii0XHfHP&index=2) - in French
* [Projet React / Redux Apprendre Redux de zéro](https://www.youtube.com/watch?v=1r6-WjzDgbM&list=PLEiMYEzpB4QsZIxBeWo9T1fCnii0XHfHP&index=3) - in French
* [React documentation](https://reactjs.org/docs/getting-started.html)
* [React Hooks API Reference](https://reactjs.org/docs/hooks-reference.html#useeffect)
* [JWT tokens and security – working principles and use cases](https://www.vaadata.com/blog/jwt-tokens-and-security-working-principles-and-use-cases/)
* [Medium article: Why MERN?](https://medium.com/geekculture/why-mern-a125cca5ab0e)
* [Webuters: Why MERN Stack is Popular for Web and Mobile Apps?](https://www.webuters.com/why-mern-stack-is-popular-for-web-and-mobile-apps)

## :file_folder: License

* N/A.

## :envelope: Contact

* Repo created by [ABateman](https://github.com/AndrewJBateman), email: gomezbateman@yahoo.com
