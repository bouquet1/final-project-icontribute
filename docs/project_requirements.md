p5-handmade-jewelries-project
Capstone Project for the Full Stack course at The Flatiron School

Project Requirements Checklist
Flask/Python API

SQLAlchemy

Models

4 models
1 many-to-many relationship
1 model has all CRUD actions (following REST conventions, follows REST routes)
CREATE (POST)
READ (GET)
UPDATE (PATCH)
DESTROY (DELETE)
User can interact with all models, directly or indirectly (no unused models).
user can click and see some reviews but can't see the name of the user who post that review or can't write a comment on that review unless signed in
React Frontend

3 client-side Routes with React Router

/sign-up

fetch GET ...com/api/v1/sign-up
fetch POST ...com/api/v1/sign-up
/login

fetch GET ...com/api/v1/login
fetch POST ...com/api/v1/login
NavBar or other UI elements that allows users to navigate between routes

Implement password hashing and authentication. This one has two differetn sides; front-end and back-end. Notes are below.

Validations implemented on frontend and backend.

For backend :

Use SQLAlchemny validations to verify and protect data on the backend.
Use forms and validations through Formik on all input. (at least one data type validation and at least one string/number format validation)
one of the models has to be a user model so sort. It should have password hashing and the authentication. that's probably be bcrypt. Password hashing: don't store plain text passwords!
Also Validation and constraints. Email is unique and NOT NULLABLE, REGEX to match email pattern. Phone number column; phone number is unique and NOT NULLABLE, REGEX to match phone number pattern. Strong password (8+, symbol, number, upper and lowercase), password confirmation match.
signup or login, logout (Routes - redirecting to login after sign up, redicrect to dashboard after login)
For frontend

Connect the client and server using fetch().
login/signup forms (email-phone regex & required, strong password, password comfirmation)
Formik controlleed form
Error handling
Plus, optonal/highly recommended requirements
Implement soemthing new that is not taught in the curriculum. maybe safety photos e.g. choose the ones has a car
Implement useContext or Redux
Fully deploy and host your project
Project Guidance
Planning
User Stories

- [ ] Note: a user should only be able to edit and delete user-specific resources if they are logged in and the creator of that resource, with the exception of high permission users such as admin roles if implemented. For example, if we consider the example described below with models of User, DogHouse, and Review, I would only be able to edit or delete the reviews that I created.

- Start by deciding on a domain for your app (such as "AirBNB for dogs"). Then, decide what user stories your app will need. It is helpful to break up your user stories between what is required for the Minimum Viable Product (MVP)Links to an external site. version of your app, and what you'd like to save for stretch features after you've met your MVP goals.

#### For Example

- MVP: As a user, I can:
  - [ ] Sign up for an account,
  - [ ] Log in to the site & remain logged in,
  - [ ] Log out,
  - [ ] View a list of all available dog houses in my area and their respective reviews,
  - [ ] Create a review for one specific dog house,
  - [ ] Modify or delete a review that I left,
  - [ ] Create a new dog house listing.
  - [ ] Stretch: As a user, I can:
  - [ ] View dog houses on a map,
  - [ ] Search dog houses based on their distance from my location,
  - [ ] Filter dog houses based on their average rating.
- Stretch: As a user, I can: - [ ] View dog houses on a map, - [ ] Search dog houses based on their distance from my location, - [ ] Filter dog houses based on their average rating.
  Models and Relationships
- After deciding on your app's user stories, you can design the models that your application will need in order to represent these user stories.

- Look at the list of your user stories, and pick out the different nouns/objects that you need to represent these user stories. These objects inform what models you need. For example, from the list above, we have:

  - User
  - Dog House
  - Review

- You can also get a sense of the relationships between the models and use that as the basis of your Entity Relationship Diagram (ERD). For example, we can tell based on the user stories above that a review belongs to a specific user — since a user is able to create a review — and a review belongs to a specific dog house.

You can use a website like dbdiagram.ioLinks to an external site. to help make an ERD and represent these relationships, or draw out something simple:
User -< Review >- DogHouse

DogHouse >- User

This is also a good time to think about what attributes your models will need. What foreign keys are needed to establish relationships? What other attributes might you need to display data in your frontend, or make other aspects of your user stories work?

Wireframes

For your frontend, it's a good idea to follow the ideas from Thinking in ReactLinks to an external site. as you're designing your React application. That means starting with a visual representation of what your application should look like, in the form of a wireframe. The wireframe should give you a basic visual representation of what each page of your application should look like, and it should capture all of your user stories.

Here are some tools for wireframing (pen and paper is also a fine choice!):

Excalidraw - basic hand-drawn wireframesLinks to an external site. Figma - professional design toolLinks to an external site. Balsamiq - professional wireframe toolLinks to an external site. Use your wireframe to plan out what components you'll need and design your component hierarchy, following the ideas from Thinking in ReactLinks to an external site..

Execution

Once you have your plan in place, and have a sense of your:

User stories Models (including relationships and attributes) Wireframes

It's time to start building! As you're building, work on each feature in vertical slicesLinks to an external site. rather than horizontal. For example, rather than building out all the models, routes and controller actions in the backend, then working on the components in the frontend and finally styling everything, work on one feature at a time, such as working on login, then displaying a list of dog houses, then leaving a review.

REMEMBER: If you try to build all your migrations, then all your models, then all your controllers, then all your fetch calls, then all your view logic you will have a bad time. Inevitably, your view logic ends up requiring changes to the underlying layers, and you end up building models that you never use. If you instead build each feature (each vertical slice) in its entirety before moving on to the next feature, you'll minimize rewriting, and end up with working features without waste.#
Add feature by feature, not model by model or layer by layer. Test each feature, add styles, and create seed data as you go (not all at once at the end).Also, remember to prioritize your MVP features. It can be tempting to try and build everything at once, but that is a sure-fire way to end up with many broken features instead of a solid core of working features.
Deploying The template project has all the starter code needed to help you deploy your application to Render. It's recommended to deploy your project early and push up changes often to ensure that your code works equally well in production and development environments.

Follow the instructions in the template to deploy your app!
