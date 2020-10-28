# Passport Authentication Codebase Tutorial

[Deployment]()

## Description

This is an in-depth tutorial on the Passport Authentication application to help onboard new developers. This tutorial will explain every file and its purpose in as fine as detail as possible. This tutorial will include details of wheter one file is dependant on other files. The code will contain line-by-line commenting for further explanation.

## Table of Contents

- [Files](#Files)

  - [config Directory](#config)

    - [middleware Directory](#middleware)

      - [isAuthenticated.js](#isAuthenticated.js)

    - [config.json](#config.json)

    - [passport.js](#passport.js)

  - [models directory](#models)

    - [index.js](#index.js)

    - [user.js](#user.js)

  - [public directory](#public)

    - [js directory](#js)

      - [login.js](#login.js)

      - [members.js](#members.js)

      - [signup.js](#signup.js)

    - [stylesheets directory](#stylesheets)

      - [style.css](#style.css)

    - [login.html](#login.html)

    - [members.html](#members.html)

    - [signup.html](#signup.html)

  - [routes directory](#routes)

    - [api-routes.js](#api-routes.js)

    - [html-routes.js](#html-routes.js)

  - [.gitignore](#.gitignore)

  - [LICENSE](#LICENSE)

  - [package.json](#package.json)

  - [README.md](#README.md)

  - [server.js](#server.js)

- [How To Add Changes](#Changes)

- [Installation](#Installation)

- [Technologies](#Technologies)

- [Dependencies](#Dependencies)

- [Credits](#Credits)

- [License](#License)

## Files

### config

This directory contains files used to configure the parameters and initial settings.

#### middleware

This directory contailes configuration files that are middleware.

##### isAuthenticated.js

This application requires users to login to access certain routes. This middleware restricts the users to certain routes that requires being logged in when the user isn't logged in. If the user tries to acess a route without being logged in, the user will be redirected to the "/" page.

#### config.json

The purpose of config.json is to define the configuration details for development, test, and production.

#### passport.js

The purpose of passport.js is to use the passport dependency, passport-local dependency, and mdoels directory to allow the user to login to the application. Passport.js takes in the user's email address and password. If there is no email inside the database, "incorrect email" is returned to the user. If the password doesn't match the email, "incorrect password" is returned to the user. If the password and email matches, the user is able to login. In order to help keep authentication state across HTTP requests, sequelize needs to serialize and deserialize the user.

### models

#### index.js

#### user.js

### public

#### js

##### login.js

##### members.js

##### signup.js

#### stylesheets

##### style.css

#### login.html

#### members.html

#### signup.html

### routes

The routes directory contains the different javascript files that supports the requests.

#### api-routes.js

This routes supports requests for APIs. It requires the models folder and the passport script file inside config. It allows users to signup for their account when they enter in their email address and password. This will be added to the database. There is also a validator to validate the information the user entered to meet the login criteria. There is a logout route and a route where the user can get back their email address and id after being logged in.

#### html-routes.js

This routes supports get requets for "/", "/members", and "/login." The path is being required for redirecting and isAuthenticated is being required to check if the user is login. If the user is login, they will be redirected to the "/members" page when they go to "/" or "/login." If the user doesn't have an account, they will be directed to the the login page. There is an authentification middlewar so the user can't access "/members" without being login and will be redirected to the signup page.

### .gitignore

The purpose of .gitignore is for git to ignore certain files inside of it. Node_modules and package-lock.json are ignored because it saves memory and the files can easily be installed with the command "npm install." .DS_Store is ignored because it can cause conflict for mac users depending on their directory settings.

### LICENSE

The purpose of the LICENSE is to allow the user to know what permission they have with using the software. For this application, the MIT LICENSE is used.

### package.json

The purpose of package.json is to the metadata for the application. It holds multiple dependencies that can be used through running "npm install" in the command the line. The dependenices for this package.json file includes bcryptjs, express, express-session, mysql2, passport, passport-local, and sequelize.

### README.md

The purpose of the README file is to provide information on how users can use the Passport Authentication application. It contains the description, tutorial, installation, technologies, dependencies, credits, and license for the app.

### server.js

The server.js is the file that is going to be run to access the application. This file is dependent on the dependencies "express", "express-session", and "passport". This file is dependent on the files inside the direcotry "models" and the directory "routes." The server.js file connects to the port and syncs to the database. It uses middleware to access the request and response objects.

## Changes

## Installation

## Technologies

- HTML
- CSS
- Javascript
- Node.js

## Dependencies

- bcryptjs
- express
- express-session
- mysql2
- passport
- passport-local
- sequelize

## Credits

David Anusontarangkul

[LinkedIn](https://www.linkedin.com/in/anusontarangkul/)
[Github](https://github.com/anusontarangkul)

This project is apart of the UC Berkeley Coding Bootcamp.

## License

Copyright <2020> <Anusontarangkul>

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

End license text.
