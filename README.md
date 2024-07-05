
# Python API Server

This is a simple Python API Server using POST to save data to MongoDB and GET requests to receive the data from MongoDB.

## Prerequisites

Before you begin, ensure you have met the following requirements:

- You have installed Python 3.6 or higher.
- You need docker to run this project.
- You need mongodb compass and postman.
  
## Create a docker network
docker network create asgnetwork

## Run Docker
docker run -d -it -p 3000:3000 --network asgnetwork --name asgn1container kajibaa/assignment1:v1

Ensure your MongoDB instance is running and accessible as configured in your Python script.
```bash
docker run --name mongodb --network asgnetwork -d -p 27017:27017 -v my_mongo_data:/data/db mongo:latest
```
## Using the Application

To interact with the application, you can use the following `curl` command to create a new item in the database:

```bash
curl -X POST http://localhost:3000/items \
     -H "Content-Type: application/json" \
     -d '{"id": "4", "name": "sandesh"}'
