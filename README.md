For this project, you will continue building an e-commerce application using your knowledge of full-stack web development. E-commerce applications are ubiquitous online and make up the back-bone of online business, making the skills used to build them invaluable for any budding entrepreneur. This project requires that you build a fully-functioning e-commerce application that allows users to register an account, browse products for sale, and complete a purchase.

Project Objectives:
Build a functioning e-commerce application using React, Node.js, and Postgres by extending your existing e-commerce REST API with an interactive client
Use Git version control
Use command line
Develop locally on your computer
Enable users to create a personal account
Enable users to create an account with a third-party service (Google, Facebook, etc)
Enable users to browse products
Enable users to complete a purchase using a payment processor (Stripe recommended)
Enable users to view order history
Deploy the application using Render
Prerequisites:
JavaScript
Git and GitHub
Command line
HTML
CSS
React




Plan your project
Visualize your end result. What is it built with? What can it do? Make sure that it satisfies all of the project objectives. The following tasks will help you identify natural break points.
Make a timeline for yourself and avoid the temptation to build things that aren’t required. Setting firm boundaries and deadlines will keep you on track and prevent scope creep.

Set up the React project
Set up the necessary folders and files for building your React frontend.
You can use create-react-app to easily set up the necessary folders and files needed for a basic React app. It is a good idea to initialize your React project as a subdirectory inside your project root directory. Remember to track your changes to your code using git.

Set up React Router
Set up React Router to be able to navigate between different pages of your app.
Refer to this documentation if you need help getting started with using React Router. Think about how you’d want to structure your files as you begin adding pages for your app. For example, you may consider having a components directory that contains all your React components.

Build the registration page
The registration page should allow the user to create a new account using a username and password. It should also include a link to the login page if the user already has an existing account.
Create a form for users to register a new account. Make sure you modify your registration endpoint handler to hash and salt the password in order to ensure secure storage! We recommend using bcryptjs to secure your passwords.
After users register an account, they should automatically be signed in as well.

Build the login page
The login page should allow the user to sign in using either a username and password or a third-party service like Google or Facebook. It should also include a link to the register page if the user does not have an existing account.
Create a form for users to sign in using a username and password. Also include buttons that can redirect users to log in using a third-party service if they choose. Remember to add functionality to the login endpoint to hash the incoming password in order to compare it correctly to the one on file.

Set up third-party login
Add the logic for handling login using a third-party service.
Passport.js makes it easy to handle user authentication using a third-party service like Google or Facebook. Look here for the various authentication strategies you can use. This will require modification of your existing REST API to support this functionality.

Enable session support
Enable session support for your application in order to maintain login state.
The express-session module is a popular choice for session management. As you implement the login functionality, you’ll want to establish a new session upon successful authentication.

Add logout functionality
Allow users to log out of their account from any page if they are signed in.
Passport.js provides a logout() function to easily terminate a login session from any route handler.

Build the products listing page
The products listing page will be the place for users to browse through the products available for sale. Each product should display a name, description, and image.
Create the React components needed to help build your page. For example, you may want a ProductList component to display the list of products and Product component for rendering a particular product.
Use the API endpoints you’ve previously created to fetch the necessary information to be displayed on your page. Make sure to enable CORS to be able to make the requests. If you want a refresher on making requests in JavaScript, you can review this module.

Build the product details page
Each product in the listings page should link to a details page containing more information about that product. The product details page should also provide functionality allowing users to add the detailed item to their carts.
Create the necessary component(s) for the details page and fetch data from your API to be displayed. Update your products listing page to link to the details page for each product.

Track cart items
On each product details page, there should be a button that allows users to add that item to their cart. Keep track of which items have been added to cart.
Leverage your cart endpoints from your REST API to add or delete products from the current active cart. Make sure you are able to distinguish between items in the current cart and items from past orders. Current cart items will be visible to the user on the checkout page and past items will be visible in order history.

Build the checkout flow
The checkout page should display the current cart items and allow users to complete their purchase.
Stripe is a popular payment processor you can use. Refer to this documentation for more information on integrating Stripe into a React project (Stripe Elements). Remember to modify your REST API endpoint for handling charges to utilize Stripe. After you finish implementing this, feel free to use test card numbers from here to test your new feature.

Allow access to protected resources
Some features on your site should only be accessible after the user logs in, such as the ability to add items to the cart or complete an order. Make sure to redirect users to the login page if they are trying to perform these tasks and are not signed in.
When trying to access protected resources, make sure the session identifier is always being passed in with your request. On the backend, check the ID to make sure the user is authorized before returning the requested information. If the user is not authorized, return a 401 Unauthorized response and redirect the user accordingly.
One option is to write an authentication middleware that can perform this ID check, and add that in front of the API endpoints that require protection.

Set up order history
Users should be able to access their order history when they are logged in, including details about the order status and purchased items.
All past order information should be made viewable to a logged-in user. Set up the pages needed for fetching and displaying the order history. Make sure to protect these resources from unauthorized access.























