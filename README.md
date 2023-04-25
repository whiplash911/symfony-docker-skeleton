## Tutorial for using Docker to create a PHP app, using nginx server, mysql and redis services

### Useful commands

#### Build from the Dockerfile and start the development environment
*docker compose -f docker-compose.yaml -f docker-compose.dev.yaml --env-file .env.local up --build -d*
###### With the -f flag we specify the docker-compose files in order, meaning that we're using docker-compose as a base, and then we're overriding with the files that come afterwards, in this case docker-compose.dev.yaml 
###### Alternatively we can extract this long command into a shell script that we run
#### Shut down the development environment
*docker compose -f docker-compose.dev.yaml down*

#### Login to Dockerhub
*docker login -u your_username*

#### Build the image, and tag it
*docker build --target app -t donchof/php-composer:1.0 -f ./php/Dockerfile .*

#### Push the image on Dockerhub
*docker push donchof/php-composer:1.0*