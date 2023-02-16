# Backend and Frontend Health API


### Clone Applications

``
cd apps
``

``
git clone https://github.com/jameelio/health-frontend.git
``

``
git clone https://github.com/jameelio/health-backend.git
``



### Apps 

- `health-frontend`: a [Vuejs App](https://vuejs.org/) app
- `health-backend`: an [NestJs](https://nestjs.com/) server

### Docker

This repo is configured to be built with Docker, and Docker compose. To build all apps in this repo:

```
# Create a network, which allows containers to communicate
# with each other, by using their container name as a hostname
docker network create app_network

# Build prod
docker-compose -f docker-compose.yml build

# Start prod in detached mode
docker-compose -f docker-compose.yml up -d
```

## Frontend UI
Open http://localhost:8080 

## Backend Api
http://localhost:3000/symptoms/:{searchTerm}

#### Example

`
curl --location --request GET 'http://localhost:3000/symptoms/head'
`

To shutdown all running containers:

```
# Stop all running containers
docker kill $(docker ps -q) && docker rm $(docker ps -a -q)

# Do not run this
# docker system prune