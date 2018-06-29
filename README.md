# AngularPlayground

This project was generated with [Angular CLI](https://github.com/angular/angular-cli) version 6.0.8.

## Development server

Run `ng serve` for a dev server. Navigate to `http://localhost:4200/`. The app will automatically reload if you change any of the source files.

## Code scaffolding

Run `ng generate component component-name` to generate a new component. You can also use `ng generate directive|pipe|service|class|guard|interface|enum|module`.

## Build

Run `ng build` to build the project. The build artifacts will be stored in the `dist/` directory. Use the `--prod` flag for a production build.

## Running unit tests

Run `ng test` to execute the unit tests via [Karma](https://karma-runner.github.io).

## Running end-to-end tests

Run `ng e2e` to execute the end-to-end tests via [Protractor](http://www.protractortest.org/).

## Further help

To get more help on the Angular CLI use `ng help` or go check out the [Angular CLI README](https://github.com/angular/angular-cli/blob/master/README.md).

# Angular playground for QUAD, part 1

Complete the Tour of Heroes tutorial. You can find it here: https://angular.io/tutorial
This will give you a basic idea of how to build and structure an Angular application.

You can just create a new local repository for this one.

# Angular playground for QUAD, part 2

The purpose of this project is to introduce you to a set of the technologies we use at QUAD. In this repository you'll find what you need to create
a sample app which uses Angular 6 for the frontend and consumes our Core API.

Fork this repo to start.

## Resources

- https://angular.io

## What you will be building?

You'll be building an user management web app which will allow you to log into a control panel and manage users inside the system.
This means you'll have to handle async requests to our API (with observables) and build a set of components that will comprise the web app.

## What you will be using?

* Angular (please use the CLI to generate components and routes)

## External dependencies

* QUAD's Core API

## Endpoints you'll need

The base API url is https://coreapi.quad.se/api

### /auth/login

Login

Method: POST

Accepts:
```
{
  username: "email@test.com",
  password: "password"
}
```

Returns:
```
{
  "data": {
    "token": "token_string"
  }
}
```

You'll need to store this token as every other request **must** use it.

### /user?limit=10&page=0&searchString=&sort=updatedAt+DESC

List users

Required headers: 

`Authorization: Bearer "token_string"`

Method: GET

Accepts: NA

Returns:
```
{
  "data": {
    "data": [ ...array of users ],
    "count": "user count"
  }
}
```

### /user/{id}

Update user

Required headers: 

`Authorization: Bearer "token_string"`

Method: PUT

Accepts: 

```
{
    "email": "cvega@18techs.com",
    "lastname": "Vega",
    "firstname": "Carlos",
    "username": "CarlosVega",
    "roles": [{
        "name": "admin"
    }],
    "cell": "12121212",
    "userID": "58496fe67d546a1c00e9db6b"
}
```

Returns:
```
{
  "data": [ ...array containing single updated user ]
}
```

### /user/{email}

Get user by email

Required headers: 

`Authorization: Bearer "token_string"`

Method: GET

Accepts: NA

Returns:
```
{
  "data": [ ...array containing the requested user ]
}
```

We don't want to delete users.

## Angular playground for QUAD, part 3

In part 3 you'll learn about state management in Angular apps and will upgrade the app built before to use `ngrx/store` or `NGXS`.

## Resources

Please enroll and complete this course https://ultimateangular.com/ngrx-store-effects, it is, hands down, the best `ngrx/store` course you'll see around.
`ngrx/store` is based of off Redux so it's trying to port concepts from functional programming into angular, which mainly uses an object oriented, reactive approach.
Because of this, `ngrx/store` can add up a bit of boilerplate and can be quite verbose.

Once you're done with the `ngrx/store` course take a look at NGSX (https://ngxs.gitbook.io/ngxs/api) and follow this tutorial: https://www.youtube.com/watch?v=SGj11j4hxmg&feature=youtu.be
This is an alternative that's a bit less verbose and more angular-y. After going through both, choose one and update the app you created in part two to use it.

## What you will be using?

* The code from part 2
* NGXS or ngrx/store (for state management, https://ngxs.gitbook.io/ngxs/api, https://github.com/ngrx/store)
