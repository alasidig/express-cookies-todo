
 # express-cookies-todo
Sample Todo App using cookie-parser
# How to run
- run `node index.js`
- open a browser on http://127.0.0.1:5000
- Open the Chrome inspector and switch to the Application tap > Storage > cookies > http://127.0.0.1
- Add tasks using the form and observe the content of the tasks cookie
- As an exercise add a button to remove the task from the cookie
- you can run it on replit [https://replit.com/@alasidig/cookies#index.js](https://cookies.alasidig.repl.co/)
# Explaination:
## index.js
This code is an example of a simple web application that allows users to create and store a list of tasks using cookies. The code uses the Express framework for Node.js and the nunjucks template engine for rendering HTML pages.
These lines of the code imports and use the cookie-parser middleware:
```js
const CookieParser = require('cookie-parser');
app.use(CookieParser());
```
This line of the code `app.route("/")` defines a route handler for the root path ("/") of the application. The route handler can handle both GET and POST requests from the client.

The next line of the code defines a callback function for handling GET requests. The function takes two parameters: req and res, which represent the request and response objects respectively. The function uses the res.render method to render a list.html file as the response. The list.html file is a template that displays the tasks stored in the cookies. The function passes an object as the second argument to the res.render method, which contains a property named tasks with the value of req.cookies.tasks. This means that the function reads the tasks from the cookies sent by the client and passes them to the template.

The next  lines of the code `.post((req,res)=> ...` defines a callback function for handling POST requests. The function also takes two parameters: req and res. The function uses the req.body.title property to get the title of the new task submitted by the client through a form. The function then creates a variable named listItems and assigns it to the value of req.cookies.tasks or an empty array if req.cookies.tasks is undefined. This means that the function either gets the existing tasks from the cookies or creates a new array if there are no tasks. The function then pushes the new task title to the listItems array and uses the res.cookie method to set a cookie named tasks with the value of listItems. This means that the function updates the cookie with the new task. Finally, the function uses the res.redirect method to redirect the client to the root path ("/") of the application. This means that after adding a new task, the client will see the updated list of tasks on the list.html page.
