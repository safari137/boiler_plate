# boiler_plate
My Custom Node Boiler Plate

Dependencies: 
- dotenv : for environmental variables
- body-parser : for reading form data and passport-local
- express
- mongoose : database ORM
- passport : Authentication
- passport-local : local authentication
- express-session : Authentication Sessions
- connect-flash : displaying messages from server side logic to view
- ejs : view engine (could substitute any other engine with minor adjustments)

This boiler plate is intended to be basic startup project with minimal dependencies for most projects.  It is also intended to follow the
MVC architectural pattern.

# server.js
- initializes most dependencies
- connects to MongoDB via mongoose
- forwards all routes to ./app/routes.js

#./app/routes.js
- forwards routes to the appropriate controllers
- In this case, the only initial controller is the userController.
- This file also has the ability to verify if the user is logged in 'isLoggedIn(req, res, next)'.  If the user is not logged in, 
they are forwarded to the "/login" route.

# controllers
- Most routes are forwarded to a controller, unless the route is only rendering a basic view page that doesn't require any server side logic.
- The controller is responsible for the middle work between the models / data and the view.
