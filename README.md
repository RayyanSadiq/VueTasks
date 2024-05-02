# VueTasks
https://github.com/RayyanSadiq/VueTasks/assets/113306690/0bb21edb-f7fa-4ea8-aa42-17045e140f4f

This is a simple CRUD application built with Vue.js that allows you to keep track and view your tasks. The application so far allows users to add, delete, and toggle reminders for tasks. The application provides a user-friendly interface for managing tasks effectively and uses Vue Router for client-side routing to navigate between different views. JSON Server is used as a placeholder for the backend, providing as a RESTful API for storing and retrieving tasks. Soon I plan on replacing JSON server with an actual RESTful application made with Spring MVC.

## Features:

- Add Task: Users can add new tasks with a title, description, and optional reminder.
- Delete Task: Users can delete tasks individually, with a confirmation prompt to ensure the action.
- Toggle Reminder: Users can toggle the reminder status of tasks, indicating whether they want to be reminded of a task or not.
- Dynamic Rendering: Tasks are dynamically rendered in the UI, providing real-time updates when tasks are added, deleted, or their reminder status is toggled.
- Task Persistence: Tasks are stored persistently using JSON Server, allowing users to access their tasks from any device or browser.
- Responsive Design: The application is designed to be responsive, ensuring a seamless user experience across various devices and screen sizes.
- Client-side Routing: Vue Router is used for client-side routing, allowing users to navigate between different views of the application without reloading the page.

## To-Do List / Upcoming Features
- [ ] Implement and connect VueTasks to A RESTful API application so I can prepare it for deployment
- [ ] Add data validation for the task's information
- [ ] Set up a user login system
 
## Tools Used:

- Vue.js: A progressive JavaScript framework used for building user interfaces. Vue.js provides a simple and flexible way to develop interactive web applications.
- Vue Router: The official router for Vue.js applications, used for client-side routing to navigate between different views of the application.
- JSON Server: A full fake REST API implemented with JSON, used as a placeholder for the backend to simulate a server environment during development.
- Fetch API: Used for making HTTP requests to the JSON Server to perform CRUD operations on tasks.
- Font Awesome: Used for adding icons to enhance the user interface and provide visual cues for actions such as adding, deleting, and toggling reminders.

## Project setup
Although the application is not ready for deployment and is not currently ready for hosting here are the steps for running and hosting the application locally on your device.

### 1.) Clone the repository to your local machine
```
 https://github.com/RayyanSadiq/VueTasks.git
```
 
### 2.) Navigate to the project directory
```
cd task-management-app
```

### 3.) Install dependencies
```
npm install
```

### 4.) Start the JSON Server
```
npm run backend
```

### 5.) Start the development server
```
npm run serve
```
### 6.) Open your web browser and visit http://localhost:8080 to view the application.
Now you should be able to play around the with application as it is hosted on you local machine. Make sure you do not have any other application or server occupying this port beforehand otherwise the server will not launch
![image](https://github.com/RayyanSadiq/VueTasks/assets/113306690/9545bd1e-a0d2-43ae-bf03-e8a96c7fc2de)

 
