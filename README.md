<div align="center">

# Cinema app 🎥

  [Description](#-project-description) • [Features](#-features) • [Technologies](#-technologies) • [Architecture](#-architecture) • [UML-diagram](#-uml-diagram-of-database) • [Running](#-how-to-run) 

</div>

## 📔 Project description
A simple REST server program engineered for cinema. this app supports: 

* registration and authentication users
* filling out shopping cart tickets and ordering
* admin management of movies, cinema halls, and etc

The program designed with a stack Spring/Hibernate behind the SOLID and OOP principles.

## 🎯 Features
The program supports two types of roles: `ADMIN` and `USER`.
The USER has the opportunity to view sessions, movies, manage their orders.
The ADMIN can manage of movies, cinema halls, and etc.

* POST: /register - all(for registration)
* GET: /cinema-halls - user/admin(for getting all cinema halls)
* POST: /cinema-halls - admin(for adding new cinema halls)
* GET: /movies - user/admin(for getting all movies)
* POST: /movies - admin(for adding new movies)
* GET: /movie-sessions/available - user/admin(for getting all available sessions to a specified movie on a specified day)
* POST: /movie-sessions - admin(for adding new movie-session)
* PUT: /movie-sessions/{id} - admin(for updating movie-session with specified id)
* DELETE: /movie-sessions/{id} - admin(for deleting movie-session with specified id)
* GET: /orders - user(for getting history for current user)
* POST: /orders/complete - user(for complete order from shopping cart)
* PUT: /shopping-carts/movie-sessions - user(for adding ticket to shopping cart)
* GET: /shopping-carts/by-user - user(for getting shopping cart)
* GET: /users/by-email - admin(for getting user by email)

## 💻 Technologies
* JDK 17      
* Maven v4.0.0
* Tomcat v9.0.50  
* MySQL  v8.0.22
* Spring WEB and Security v5.2.2
* Hibernate v5.4.27  

## ⚙ Architecture
* classes in dao dir are responsible for working with our db;
* classes in service are responsible for the execution of logic;
* classes in controller dir handle HTTP requests;

## 🔗 UML-diagram of database
![UML diagram](img/CinemaAppUml.png)

## ▶️ How to run
1. Specify your current URL of your db, user, password and JDBC driver in the appropriate variables in [`this file`](src/main/resources/db.properties);
2. For running use Servlet Container like Apache `Tomcat`(recommend to use `version 9.0.50`);
3. First user with the role of `ADMIN`, email - `admin@i.ua` and password - `admin123` will be created when you run app.