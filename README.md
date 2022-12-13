# Bransby API docker-compose

This repo contains a docker-compose file that spins up the Bransby rest-api and a postgres database, with a storage volume.

This serves as the 'back-end' of the Bransby Training Tracker application.


### Install docker

Docker is required to run the database, storage and rest-api.

It can be run from a desktop appplication or the command line. 

Docker Compose is also required to carry out the instructions contained in the `docker-compose.yaml`.

Docker installation varies across operating systems - please refer to the documentation.

https://www.docker.com/get-started/

To test if Docker and Docker Compose are installed on your command line use the following commands to obtain their versions.

```bash
docker -v
docker-compose -v
```


### Add environment variables


`docker-compose.yaml` is annotated with instructions on where to add the required user-defined environment variables, such as the database password. 

These should be added in the following format:
```yaml
environment:
      - DB_USER=bransby 
      - DB_PASSWORD=password
      - DB_NAME=equine-training-tracker-db 

```

### Spin up the application

To run the application: 
- ensure that your command line's present directory is the same as the one in which the `docker-compose.yml` file is stored.

- use `docker-compose up` to tell docker to use that file to create the application from the command line. This commmand should launch the applications and generate logs within the terminal, so it's useful for troubleshooting on an initial launch. `docker-compose up -d` will launch the application in 'detatched' mode: it will  run in the background of the terminal, without any output.  

If it's all worked, the database and rest-api should be accessible from Docker Desktop (if it's installed) or the CLI - use `docker ps` to list containers that are running.


### Swagger

The api is available on localhost:8080.

It is documented using OpenAPI/Swagger, which can be accessed at http://localhost:8080/swagger-ui/#


