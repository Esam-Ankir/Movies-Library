# Movies-Library - Version 1.0
 
**Author Name**: Esam Ankir

## WRRC
![WRRC](./images/WRRC2.jpg)
![WRRC](./images/WRRC.jpg)

## Overview
We will build a movie app that can check the latest movies based on categories and set up database and read and save data to it.

## Getting Started
1. require the package
2. create an Express app
3. the server is listening on port 3000
4. creating a route:app.METHOD(PATH, HANDLER)
5. functions

## For Database
1. Creating the database
- in terminal: make sure the sql server is running
- psql
- CREATE DATABASE databasename;
- \l will list the databases
- \q to quit psql
2. Creating the table
- create a schema.sql file in my project
- CREATE TABLE table_name (
    column1 datatype,
    column2 datatype,
    column3 datatype,
   ....
);
3. Connecting the database with the table

- psql demo2 to connect to my db
- \d to describe the table
- \q to quit
- psql -d demo2 -f schema.sql
4. Write qureis in my server:

- npm install pg
- In index.js:
const url="postgres://username:password@localhost:5432/databaseName" // store it in the .env file
// create a new client instance
const { Client } = require('pg')
const client = new Client(url)
// connect to db
client.connect().then(() => {

    app.listen(PORT, () => {
        console.log(`Server is listening ${PORT}`);
    });
})
- use client.query() to do CRUD



## Project Features
1. Home Page Endpoint: /
a. Create a route with a method of get and a path of /. The callback should use the provided JSON data.
b. Create a constructor function 
2. Favorite Page Endpoint: “/favorite”
3. Handle errors
a. Create a function to handle the server error (status 500)
b. Create a function to handle "page not found error" (status 404)
4. Create GET request to the 3rd party API for these endpoints:
 a.  /trending : Get the trending movies data from the Movie DB API
 b.  /search: Search for a movie name to get its information
