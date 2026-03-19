# FakeBnb

A practice project built as a refresher, It is a Airbnb clone where users can sign up, log in, browse listings, create their own listings, and leave reviews.

---

## Getting It Running

Follow these steps in order.

**1. Install dependencies**

```
npm install
```

**2. Make sure MongoDB is running locally on port 27017**

If it is not already running, start it with:

```
mongod
```

**3. Seed the database with sample listings**

```
node init/index.js
```

You should see the following output in the terminal:

```
Connected to DB: mongodb://127.0.0.1:27017/fakebnb
Cleared existing listings
Inserted 30 listings
Connection closed. Done.
```

**4. Verify the data was added (optional)**

Open a new terminal and run:

```
mongosh
use fakebnb
db.listings.find()
```

You should see about 30 listing documents printed out. If you do, the data is in correctly.

**5. Start the server**

```
node app.js
```

You should see:

```
Connected to DB
Server is listening on port 8080
```

**6. Open the app**

Go to `http://localhost:8080` in your browser. You will land on the home page. From there you can sign up, log in, and browse listings.

---

## Tech Stack

| Technology | What it is used for |
|---|---|
| Node.js | Runtime environment for running JavaScript on the server |
| Express.js | Web framework for handling routes, middleware, and HTTP requests |
| MongoDB | NoSQL database for storing listings, reviews, and users |
| Mongoose | ODM library for defining schemas and interacting with MongoDB |
| EJS | Templating engine for rendering HTML pages on the server |
| ejs-mate | Adds layout support to EJS so pages share a common boilerplate |
| Passport.js | Authentication middleware for handling login sessions |
| passport-local | Strategy for authenticating with a username and password |
| passport-local-mongoose | Mongoose plugin that adds authentication methods directly to the User model |
| express-session | Manages user sessions across requests |
| method-override | Allows HTML forms to send PUT and DELETE requests |
| Joi | Schema validation library used to validate listing and review form data before saving |
| Bootstrap 5 | CSS framework for styling and layout |

---

## Project Structure

```
FakeBnb/
├── app.js               -- entry point, sets up middleware and starts the server
├── schema.js            -- Joi validation schemas
├── models/              -- Mongoose models (Listing, Review, User)
├── controllers/         -- business logic for each resource
├── routes/              -- URL routing, maps paths to controllers
├── views/               -- EJS templates
│   ├── layouts/         -- shared boilerplate layout
│   ├── includes/        -- navbar and footer partials
│   ├── listings/        -- listing pages (index, show, new, edit)
│   └── users/           -- login and signup pages
├── middleware/          -- custom middleware (validation)
├── public/              -- static files (CSS, JS)
├── utils/               -- helper utilities (error class, async wrapper)
└── init/                -- database seeding script and sample data
```

---

## About This Project
Follows an MVC pattern. The routes folder is kept thin and only maps URLs to controller functions.

This was a boring practice project and I hated every second of it.

No image upload support, no user authorization checks on listings, but there is Basic Joi validation, and the session secret is hardcoded using hashing, salting, cookies. 
