# Tutorial

https://docs.docker.com/language/nodejs/build-images/

## Build

docker build --tag node-docker .

### View images

docker images

### Tag images

docker tag node-docker:latest node-docker:v1.0.0

### Remove image tag

docker rmi node-docker:v1.0.0
Untagged: node-docker:v1.0.0

### Run image in a container

docker run --publish 8000:8000 node-docker

### Run image in detached mode

docker run -d -p 8000:8000 node-docker

### Post to the sever

curl --request POST \
  --url http://localhost:8000/test \
  --header 'content-type: application/json' \
  --data '{"msg": "testing"}'
{"code":"success","payload":[{"msg":"testing","id":"dc0e2c2b-793d-433c-8645-b3a553ea26de","createDate":"2020-09-01T17:36:09.897Z"}]}

### List containers

docker ps

### Stop container

docker stop jovial_bouman

### Remove docker image

docker rm jovial_bouman

### Name a container

docker run -d -p 8000:8000 --name rest-server node-docker


## Local database and containers

https://docs.docker.com/language/nodejs/develop/#local-database-and-containers


## Docker compose

docker compose -f docker-compose.dev.yml up --build

### Curl requests

curl --request GET --url http://localhost:8000/notes

## Run your Tests using Node.js and Mocha frameworks

### Docker command to start the container and run tests

docker compose -f docker-compose.dev.yml run notes npm run test

### Run tests with test in docker file FROM base as test

docker build -t node-docker --target test .

### Configure CI/CD for your application

Setup GitHub Actions workflow to an existing Docker project

### Deploy your app 

Finished at this point in the tutorial

https://docs.docker.com/language/nodejs/deploy/
