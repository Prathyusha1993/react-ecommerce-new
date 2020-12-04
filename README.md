### Demo: https://react-ecommerce-new.vercel.app/

# Learn More About React-Ecommerce 

## Requirement Steps
- ReactJS : Fast development with reusable UI components
- React Context API : fro state managment where provides a way to pass data through the component tree without having to pass props down manually at every level.
- Bulma : this will apply style sheet across all the component in the appliaction.


In this application, we'll use React Router to handle the routing, json-server, json-server-auth to create fake backend to handle authentication. we also need axios for making ajax request, jwt_decode so that we can parse the JWT that our back end will respond and bulma css framework

- npm install react-router-dom
- npm install json-server and json-server-auth
- npm install axios
- npm install jwt_decode
- npm install bulma

## Work Breakdown

We have to breakdown the work into smaller stories to be worked to collaborate with the team. In this phase, we go through low level details to make sure we have all the necessary info to build the application, and find out proactively if there are any challenges.

According to the designs, the following React components and interactions have been identified

1. React Components
    1. Login - contains details of login page using json-server-auth
    2. ProductList - contains list of products with details like name, price, stock, shortDesc, description.
    3. ProductItem - give the more info about product like amount, stock, img of the product etc..
    4. AddProduct - you can add the product to list of product items
    5. Cart - contains cart info details like how many items are avaliable for checkout and also clearcheckout button to clear the list of items in the cart
    6. cartItem - gives the information about item present in the cart as item name, price, description etc.

### Context API :

First, we define the context data and methods using the Context.Provider component. The data and methods are passed as a property, value, on the Provider component to replace the object given on the context creation.

### Router

our application’s routes using the Switch and Route components. We also create the app’s navigation menu, with each link using the Link component provided in the React Router module.

### JSON-server
creating two resources - users and products. Looking at the users resource, you’ll notice that each user has an ID, an email address and a password. The password appears as a jumble of letters and numbers, as it’s encrypted using bcryptjs.

- username: admin@example.com   (for login)
- password: password

- to start json server by using following command from root of the project:
- ./node_modules/.bin/json-server-auth ./backend/db.json --port 3001

This will start json-server on http://localhost:3001. Thanks to the json-server-auth middleware, the users resource will also give us a /login endpoint that we can use to simulate logging in to the app.

Let’s try it out using https://hoppscotch.io. Open that link in a new window, then change the method to POST and the URL to http://localhost:3001/login. Next, make sure the Raw input switch is set to on and enter the following as the Raw Request Body:

{
  "email": "regular@example.com",
  "password": "password"
}

Click Send and you should receive a response (further down the page) that looks like this:

{
  "accessToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJlbWFpbCI6InJlZ3VsYXJAZXhhbXBsZS5jb20iLCJpYXQiOjE2MDE1Mzk3NzEsImV4cCI6MTYwMTU0MzM3MSwic3ViIjoiMSJ9.RAFUYXxG2Z8W8zv5-4OHun8CmCKqi7IYqYAc4R7STBM"
}


### Login details : 

Log in as admin (email: admin@example.com, password: password) and ensure that you see an Add Product button in the navigation. Navigate to this page, then use the form to create a couple of new products. Finally, head back to the main page and make sure the new products are showing up in the product list.


## Deploying your project

 There are a number of ways to host your project for free. I used [Vercel](https://bit.ly/fem-vercel) as it's an amazing service and extremely simple to get set up with. If you'd like to use Vercel, here are some steps to follow to get started:

1. [Sign up to Vercel](https://bit.ly/fem-vercel-signup) and go through the onboarding flow, ensuring your GitHub account is connected by using their [Vercel for GitHub](https://vercel.com/docs/v2/git-integrations/vercel-for-github) integration.
2. Connect your project to Vercel from the ["Import project" page](https://vercel.com/import), using the "From Git Repository" button and selecting the project you want to deploy.
3. Once connected, every time you `git push`, Vercel will create a new [deployment](https://vercel.com/docs/v2/platform/deployments) and the deployment URL will be shown on your [Dashboard](https://vercel.com/dashboard). You will also receive an email for each deployment with the URL.

###  Technical Details
This project was bootstrapped with Create React App.

Check [here](TechnicalDetails.md) for details on how to run and contribute to the app.