
# REST API 
## Description
A simple implementation of CRUD REST API in TypeScript using Node.js, Express, PostgreSQL (containerized with Docker) and TypeORM.

## Prerequisites

To run the API the following items are needed: 

* Node.js and NPM
* TypeScript
* Docker

## Dependencies
After handling the installation of the prerequisites, take care of installing the dependencies. 

``` bash
$ npm install express typeorm reflect-metadata pg
```
Development dependencies: 

``` bash
$ npm install typescript nodemon ts-node-dev @types/express --save dev
```
## Configuring environment

In the root folder, create a file named `.env`.

For the `.env` file, add the following information and set the values to the variables as desired. Here goes an example: 

    DB_HOST=localhost
    DB_PORT=5432
    DB_USER=postgres
    DB_PASSWORD=postgres
    DB_NAME=restapi_ts

    PORT=3000 

Note that in the `docker-compose.yaml` file, the enviorment variables are exposed. It is **not safe** to expose your credentials. The usage of a `docker.env` file is encouraged. 

## Running the migrations

In your terminal, go to the root folder of the application and run the following script to generate the migations:

```bash
$ npm run migration:generate
```

And right after that: 

```bash
$ npm run migration:run
```

## Running the server
Alright alright, now that we are all set, lets get it up and running! 


To get our `PostgreSQL` container running on the background, run the following command (if you rather not have it running detached, open another terminal and run the command without the `-d` flag): 

```bash
$ docker compose up -d
```

For the API, run the following script: 

```bash
$ npm run dev
```

And there you go! 

You can use `Postman` to test the endpoints, or use it as you like it! :) 