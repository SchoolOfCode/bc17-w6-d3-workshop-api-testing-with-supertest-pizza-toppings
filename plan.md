### Ticket 1 - Familiarity

Some questions that might help guide your exploration:

- What endpoints and types of requests does this API support?

- What's the main purpose of the `db/helpers.js` file?
  The db/helpers.js file serves as a utility module for managing the users table in the database. Its main purposes are:
  Creating the users table if it does not exist.
  Dropping the users table if it exists.
  Populating the users table with data.
  Resetting the users table by dropping, recreating, and repopulating it.

- What's the main purpose of each file in the `users` folder?

  ### users.router.js:

  Defines user-related routes and connects them to the controller functions (GET, POST, DELETE).
  These routes are connected to the appropriate controller functions from users.controller.js.

  ### users.controller.js: Contains the logic for handling user-related requests and calls the model functions.

  Functions like getUsers, getUserById, createUser, and deleteUserById process incoming requests, call the necessary model functions, and send responses back to the client.
  These functions are imported and used in users.router.js.

  ### users.model.js: Interacts with the database to perform CRUD operations on the users table.

  This file contains the functions that directly interact with the database.
  Functions like getUsers, getUsersByUsername, getUserById, createUser, and deleteUserById perform SQL queries to fetch, insert, and delete data from the users table.
  These functions are imported and used in users.controller.js.

- Where and how are the files in the `users` folder used within the overall API and Express app?

  ### how the files in the users folder are used within the overall API and Express app, based on the content of server.js and app.js.

  The server.js file is responsible for starting the server. This file imports the Express app from app.js and starts the server on port 5010. It also logs a message to the console indicating that the server is running.

  The app.js file sets up the Express application, middleware, and routes.
  This file sets up the Express app with middleware for logging (morgan) and JSON parsing. It also defines routes for health checks and user-related operations. Error handlers are included for 404 (not found) and 500 (server error) responses.

  users.router.js: Defines the routes for user-related operations. Imported and used in app.js with the path /api/users.
  users.controller.js: Contains the functions that handle the logic for user-related routes. Functions from this file are imported and used in users.router.js

  users.model.js: Contains the functions that interact with the database for user-related operations. Functions from this file are imported and used in users.controller.js.

- What endpoints/operations does the API support?

- What's the purpose of the `vitest.config.js` file?
  The vitest.config.js file configures the Vitest testing framework to load environment variables from a .env file before running any tests. This setup ensures that all tests have access to necessary environment variables, providing a consistent testing environment and preventing issues related to missing or incorrect configurations.
