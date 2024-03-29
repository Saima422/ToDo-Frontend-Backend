# Links 
 ### App Links
  * [ToDo Github Link (Dist)](https://saima422.github.io/ToDo-Frontend-Backend/)
  * [ToDo Github Link](https://saima422.github.io/Todo-Frontend-Integrated-with-Backend/)
  * [ToDo Netlify Link](https://hopeful-tesla-59c08e.netlify.app/)
  * [ToDo Backend Server](https://rocky-ocean-88181.herokuapp.com/)

 ### Repo Links
  * [Frontend](https://github.com/Saima422/Todo-Frontend-Integrated-with-Backend )
  * [Backend](https://github.com/Saima422/ToDo-Backend-Node.js)

# ToDo App (Frontend)
Todo-List App makes API calls to server for storing and maintaining ToDo's.

## Introduction

A simple frontend for ToDo Application created with Vanilla JS and integrated with a backend(uses file system for storage) which is hosted on heroku. Built with an aim to learn and implement creation of a frontend with a given backend. Todo Application supports functionalities of Adding, Updating, marking as Completed and Deleting a Todo. The application makes API calls to the backend for the same.

## Getting Started

These are instructions to set up your project locally.
To get a local copy up and running follow these simple steps.

### Prerequisites

To clone and run this application, you'll need [Git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git) 

### Installation

From your command line:

1. Clone the repo
   ```sh
   $ git clone https://github.com/Saima422/Todo-Frontend-Integrated-with-Backend.git
   ```
2. Open the index.html with Live Server to get the Frontend Up and Running


## Folder Structure
```
.
├── assest
│   └── icon.ico
├── dist
│   └── css
│       ├── styles.css
│       └── styles.css.map
├── index.html
├── README.md
├── src
│   ├── actions
│   │   └── domOperations.js
│   ├── apiCalls
│   │   └── taskApi.js
│   ├── app.js
│   └── components
│       └── task.js
└── styles
    └── styles.scss
```
## Application View
![](https://saima422.github.io/Image-JSON-Data-Repo/images/todo-list-app.png)

## Scope and Functionality

#### Features:
* Persistent Data 
* Add a New Todo
* Update a Todo 
* Mark a Todo as Completed
* Delete a Todo

#### Remaining Todo: 
* User login and registration page.
* User Authentication.
* Each User should have access to only their tasks.

## Referred Resources
* [HTTP requests](https://www.freecodecamp.org/news/here-is-the-most-popular-ways-to-make-an-http-request-in-javascript-954ce8c95aaa/)
* [Using Fetch [MDN Web Docs]](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API/Using_Fetch)
* [async-await [MDN Web Docs]](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Asynchronous/Async_await)

## Contact

* Author - Saima Sayed 
* [Connect on LinkedIn](https://www.linkedin.com/in/saima-sayed-6482481b9/)
* [Project Resources (Frontend))](https://github.com/Saima422/Todo-Frontend-Integrated-with-Backend)
* [Github Live Link](https://saima422.github.io/Todo-Frontend-Integrated-with-Backend/)
* [Netlify Live Link](https://hopeful-tesla-59c08e.netlify.app/)



## Also Refer
You can also refer to the backend Todo-List server integrated with this frontend repo <br>
* [Todo-List Backend Repo](https://github.com/Saima422/ToDo-Backend-Node.js)

<br>
<br>

<hr>

# ToDo App (Backend)
#### Backend server for ToDo Application created with Node.js<br>

## Introduction

A simple backend server for ToDo Application created with Node.js and using File System(JSON File) for storing Data. Built with an aim to provide a backend for Todo Application. Server supports API calls for Adding, Fetching and Deleting Todo.

## Technologies

* [Node.js v14.17.4](https://nodejs.org/en/)
* [express v4.17.1](https://www.npmjs.com/package/express)
* [uniqid v5.3.0](https://www.npmjs.com/package/uniqid)

## Getting Started

These are instructions to set up your project locally.
To get a local copy up and running follow these simple steps.

### Prerequisites

To clone and run this application, you'll need [Git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git) and [Node.js](https://www.digitalocean.com/community/tutorials/how-to-install-node-js-on-ubuntu-18-04) (which comes with npm) installed on your computer.

### Installation

From your command line:

1. Clone the repo
   ```sh
   $ git clone https://github.com/Saima422/ToDo-Backend-Node.js
   ```
2. Install NPM packages
   ```sh
   $ npm install
   ```
4. Run the app
   ```JS
   $ npm run start
   ```


## Endpoints
### 1. GET all Todo's

Returns json data containing objects of each Todo.

* **URL**

	`/tasks`

* **Method:**

	`GET`

*  **URL Params**

	**Required:**

	`None`

* **Data Params**

	`None`

* **Success Response:**

	 **Code:** 200 <br />
	**Content:**

  ```sh
  {
    "message": "successfully fetched all tasks",
    "data": [
      {
        "taskId": "9vf61mv7ks5rgz6m",
        "content": "First task for backend",
        "createdAt": "Some date ",
        "updatedAt": "Some date ",
        "isCompleted": "false"
      },
      {
        "taskId": "9vf62iwnks67y6q5",
        "content": "Task 5",
        "createdAt": "Some date ",
        "updatedAt": "Some date ",
        "isCompleted": "false"
      }
    ]
  }
  ```

* **Sample Call:**
  ```sh
  $.ajax({
      url: "/tasks",
      dataType: "json",
      type : "GET",
      success : function(r) {
      console.log(r);
    }
  });
  ```
  OR
  ```sh
  fetch('/tasks')
    .then(response => response.json())
    .then(data => console.log(data));
  ```

* **Example:**

  ![](https://saima422.github.io/Image-JSON-Data-Repo/images_Todo-Backend_Readme/getall_image.png)


### 2. GET Todo by ID

Returns json data containing objects of Todo ID provided.

* **URL**

	`/tasks/taskId`

* **Method:**

	`GET`

*  **URL Params**

	**Required:**

	`taskId =  [String]`

* **Data Params**

	`None`

* **Success Response:**

	 **Code:** 200 <br />
	**Content:**
  ```sh
  {
    "message": "successfully fetched task",
    "data": {
      "taskId": "9vf617xbks7t0ads",
      "content": "Some Task is completed",
        "createdAt": "10/08/21 22:07:30",
        "updatedAt": "11/08/21 12:30:15",
        "isComplete": true
    }
  }
  ```

* **Error Response:**

  **Code:** 404 NOT FOUND <br />
    **Content:** `{
    "message": "Element Not Found",
    "error": "Invalid Id"
}`

* **Sample Call:**
  ```sh
  $.ajax({
      url: "/tasks/9vf617xbks7t0ads",
      dataType: "json",
      type : "GET",
      success : function(r) {
      console.log(r);
    }
  });
  ```
   OR
  ```sh
  fetch('/tasks/taskId')
    .then(response => response.json())
    .then(data => console.log(data));
  ```


* **Example:**

  ![](https://saima422.github.io/Image-JSON-Data-Repo/images_Todo-Backend_Readme/getbyid_image.png)

### 3. Add a new Todo

Returns json data containing the message and added task.

* **URL**

	`/tasks`

* **Method:**

	`POST`

*  **URL Params**

	**Required:**

	`None`

* **Data Params**

	`{ "content": [String], "createdAt": [Time(HH MM) Date(DD/MM/YY)], "updatedAt": [ime(HH MM) Date(DD/MM/YY)}`

* **Success Response:**

	 **Code:** 200 <br />
	**Content:**
  ```sh
  {
    "message": "successfully Added task",
    "data": {
      "taskId": "9vf617xbks7t0ads",
      "content": "Some Task is completed",
        "createdAt": "10/08/21 22:07:30",
        "updatedAt": "11/08/21 12:30:15",
        "isComplete": false
    }
  }
  ```

* **Error Response:**

  * **Code:** 404 NOT FOUND <br />
    **Content:** `{
    "message": "Invalid Request",
    "error": "Invalid Request"
}`

	OR
  * **Code:** 400 <br />
    **Content:** `{
    "message": "Invalid Request",
    "error": "Invalid Request"
}`

	OR

  * **Code:** 500<br />
    **Content:** `{
    "message": "An error occurred while writing file",
    "error": error that has occurred
}`


* **Sample Call:**
  ```sh
  $.ajax({
      url: "/tasks",
      dataType: "json",
      type : "POST",
      data : {"content": "some task", "createdAt": "10/08/21 22:07:30", "updatedAt": ""}
      success : function(r) {
        console.log(r);
      }
  });
  ```
   OR
  ```sh
  fetch('/tasks', {
                    method: 'POST',
                    headers: {
                        'Content-Type': 'application/json',
                    },
                    body: JSON.stringify(your data variable),
                  }
        )
    .then(response => response.json())
    .then(data => console.log(data));
  ```

* **Example:**

  ![](https://saima422.github.io/Image-JSON-Data-Repo/images_Todo-Backend_Readme/addtodo_image.png)

### 4. Update an existing Todo

Returns json data containing the message and Updated task.

* **URL**

	`/tasks/taskId`

* **Method:**

	`POST`

*  **URL Params**

	**Required:**

	`id = [String]`

* **Data Params**

	`{ "content": [String], "createdAt": [Time(HH MM) Date(DD/MM/YY)], "updatedAt": [ime(HH MM) Date(DD/MM/YY)}, "isComplete": [Boolean]}`

* **Success Response:**

	 **Code:** 200 <br />
	**Content:**
  ```sh
  {
    "message": "successfully updated task",
    "data": {
      "taskId": "9vf617xbks7t0ads",
      "content": "Some Task is completed",
        "createdAt": "10/08/21 22:07:30",
        "updatedAt": "11/08/21 12:30:15",
        "isComplete": false
    }
  }
  ```

* **Error Response:**

  * **Code:** 404 NOT FOUND <br />
    **Content:** `{
    "message": "Invalid Request / Task with id not found",
    "error": "Invalid Request"
}`

	OR
  * **Code:** 400 <br />
    **Content:** `{
    "message": "Invalid Request",
    "error": "Invalid Request"
}`

	OR

  * **Code:** 500<br />
    **Content:** `{
    "message": "An error occured while writing file during update",
    "error": error that has occurred
}`


* **Sample Call:**
  ```sh
  $.ajax({
      url: "/tasks/9vf617xbks7t0ads",
      dataType: "json",
      type : "POST",
      data : {"content": "some task", "createdAt": "10/08/21 22:07:30", "updatedAt": "11/08/21 12:30:15", "isComplete": true}
      success : function(r) {
        console.log(r);
      }
  });
  ```
  OR
  ```sh
  fetch('/tasks/taskId', {
                    method: 'POST',
                    headers: {
                        'Content-Type': 'application/json',
                    },
                    body: JSON.stringify(your data variable),
                  }
        )
    .then(response => response.json())
    .then(data => console.log(data));
  ```


* **Example:**

  ![](https://saima422.github.io/Image-JSON-Data-Repo/images_Todo-Backend_Readme/update_image.png)

### 5. Delete an existing Todo

Returns json data containing the message that the task is deleted.

* **URL**

	`/tasks/taskId`

* **Method:**

	`DELETE`

*  **URL Params**

	**Required:**

	`id = [String]`

* **Data Params**

	`None`

* **Success Response:**

	 **Code:** 204 <br />
	 

* **Error Response:**

  * **Code:** 404 NOT FOUND <br />
    **Content:** `{
    "message": "Task with id not found",
}`

	OR

  * **Code:** 500<br />
    **Content:** `{
    "message": "An error occured while writing file during delete",
    "error": error that has occurred
}`


* **Sample Call:**
  ```sh
  $.ajax({
      url: "/tasks/9vf617xbks7t0ads",
      dataType: "json",
      type : "DELETE",
      success : function(r) {
        console.log(r);
      }
  });
  ```
  OR
  ```sh
  fetch('/tasks/taskId', {
                    method: 'DELETE',
                  }
        )
    .then(response => response.json())
    .then(data => console.log(data));
  ```

* **Example:** 

  ![](https://saima422.github.io/Image-JSON-Data-Repo/images_Todo-Backend_Readme/delete_image.png)

## POSTMAN
View all Sample Requests in POSTMAN.<br>

[![Run in Postman](https://run.pstmn.io/button.svg)](https://app.getpostman.com/run-collection/9aeb37683d33c80c8b18?action=collection%2Fimport)

## Folder Structure
```
├── app.js
├── controllers
│   └── taskController.js
├── data
│   └── tasks.json
├── models
│   └── taskModel.js
├── package.json
├── package-lock.json
├── routes
│   └── taskRouter.js
└── utils
    └── sendResponse.js
```

## Scope and Functionality

#### Features:
* Get all Todos
* Get a Todo with specific ID
* Add a New Todo
* Update an existing Todo by providing Todo ID
* Delete an existing Todo by providing Todo ID

#### Remaining Todo: 
* Add a Database for storing the Todos/Tasks

## Sources

* [Node.js Documentation](https://nodejs.org/dist/latest-v14.x/docs/api/)
* [Node.js - MDN Web Docs](https://developer.mozilla.org/en-US/docs/Glossary/Node.js?retiredLocale=hu)
* [Introduction to Node.js](https://nodejs.dev/learn)

## Contact

Author - Saima Sayed 
<br>
Project Resources (Backend) - https://github.com/Saima422/ToDo-Backend-Node.js
<br>
LinkedIn - https://www.linkedin.com/in/saima-sayed-6482481b9/

## Also Refer
You can also refer to the fontend Todo-List project integrated with this backend repo <br>
[Todo-List Frontend Repo](https://github.com/Saima422/Todo-Frontend-Integrated-with-Backend)<br>
[Todo-List Frontend Demo](https://hopeful-tesla-59c08e.netlify.app/)



