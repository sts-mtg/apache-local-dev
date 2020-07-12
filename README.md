## container build and up
docker-compose up -d

## Log into apache container
docker-compose exec apache bash

## container down
docker-compose down

## Rebuild Container and up
docker-compose up -d --build
