# React Requests - Pirate API Quiz

## Learning Objectives

- Understand the structure and the flow of data through the pirates application.
- Investigate the next steps to be able to POST and PATCH.
- Answer the questions below.

# Intro



For this homework, your task is to run both the client and the server for the pirates application and be able to navagite the code gaining a foundation to build on for tomorrows lesson. Dont worry about the React router elements of the app such as <Router> and <Switch> for now.

First, run the piratesServiceEnd.
> Note that in application.properties we have added at the bottom:
server.servlet.context-path=/api
This will help us differentiate our backend routes from out front end a bit more.

Then run your front end by using "npm install" and "npm start". On http://localhost3000/pirates you should see a list of pirates rendered to the page.

> Another Note: our requests are going to "/api/pirates" etc. If we were to specify localhost:8080/api/pirates we will get CORS issues that would need to be dealt with in the backend. A better way to get around this will be to use a proxy. By default, "/api/pirates" will take us to "localhost:3000/api/pirates" which is not what we want. In the package.json, we have set up a proxy to send our requests from "localhost:8080", rather than reacts "localhost:3000".
```js
  "proxy": "http://localhost:8080/"
```

# Requesting All Pirates

Question 1

Which component is responsible for requesting all the pirates?

* PirateContainer.js

Question 2

Which hook do we use to carry out the requestAll() method and when does it get triggered?

* useEffect(), executes when the page gets loaded or refreshed. 

Question 3

The requestAll() method creates a new instance of Request in order to gain the functionality to carry out various forms of request. Where is the Request class?

* It is located in the helpers folder.

Question 4

Which method are we using from the Request class here?

* get(url)

Question 5

The PirateList component is in charge of rendering a list of pirate components. What is the pirateNodes function returning?

* It returns a list item of Pirate component

# Viewing a Single Pirate


Question 1

In the browser, when we click on one of the pirates names in the pirate list, our app renders a PirateDetail component. PirateDetail is in charge of rendering the information for a single pirate. But where is it getting its props passed down from?

* PirateContainer

Question 2
 ```js
 if (!pirate){
  return "Loading..."
}
 ```
What is the purpose of this code in PirateDetail?

* If theres a async issue and the prop is not passed down in time before the component PirateDetail renders, it will display the string ???Loading??????


Question 3

In PirateDetail, to delete a pirate, we have a button with a listener "onClick" which triggers a function called "handleDelete". The handleDelete function uses a function onDelete. Where is it receiving onDelete from?

* PirateContainer.js is passing down the function handleDelete as onDelete to PirateDetail. 


# Bonus Points Questions


Question 1

In PirateContainer, what does Promise.all return?

* It returns an array of JSON???s which then get set to the relevant useState variables.

Question 2

Ideally, we want our state to live at the top of our component chain, except in one other scenario. This is when our component contains a, what?

* A form.
