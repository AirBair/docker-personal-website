# Docker Compose for my personal website (Symfony Flex w/ Webpack Encore)


Intended to be running behind a reverse proxy which map ndd.tld -> localhost:defined_port

## Requirements

- [Docker](https://docs.docker.com/) (v18.06+)
- [Docker Compose](https://docs.docker.com/compose/) (v1.22+)

## Installation

### 1 - Configure the .env file

Copy the file `.env.dist` to `.env` & complete it with the required credentials & configuration.


### 2 - Set-up the symfony project

Clone the symfony project inside a folder named `symfony`

Follow instructions from the symfony project, taking into account :
- `php` & `composer` instructions have to be executed with the **php container**
    * Ex: `docker-compose run --rm php php <command>`
    * Ex: `docker-compose run --rm php composer install`
- `yarn` instructions have to be executed with the **encore container**
    * Ex: `docker-compose run --rm encore sh -c "yarn install && yarn build"`


### 3 - Build and run

From this directory, start up services by running `docker-compose up -d`


## Upgrade

To upgrade services images to a newer version, from this directory, run :

```
docker-compose pull
docker-compose up -d
```

## License

This software is published under the [MIT License](LICENSE)
