# commands

# create docker network
docker network create mongo-network

## start mongodb
docker run -d \
-p 27017:27017 \
-e MONGO_INITDB_ROOT_USERNAME=admin \
-e MONGO_INITDB_ROOT_PASSWORD=password \
--net mongo-network \
--name mongodb \
mongo

## start mongo-express
docker run -d \
-p 8081:8081 \
-e ME_CONFIG_MONGODB_ADMINUSERNAME=admin \
-e ME_CONFIG_MONGODB_ADMINPASSWORD=password \
-e ME_CONFIG_MONGODB_SERVER=mongdob \
--net mongo-network \
--name mongo-express \
mongo-express

## create database in mongo-express
open mongo-express from browser

    http://localhost:8081

create `my-db` _db_ and `my-collection` _collection_ and _document_ with `{myid: 1, data: "some dynamic data loaded from db"}` in mongo-express
    

Access you nodejs application UI from browser

    http://localhost:3000
