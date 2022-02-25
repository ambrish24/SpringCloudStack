
# Introduction

1.  A Spring Cloud Config server that is deployed as Docker container and can manage a services configuration information using a file system/ classpath or GitHub-based repository.
2.  A licensing service that will manage licensing data used within Ostock.
3.  A Postgres SQL database used to hold the data.

## Initial Configuration
1.	Apache Maven (http://maven.apache.org)  All of the code examples in this book have been compiled with Java version 11.
2.	Git Client (http://git-scm.com)
3.  Docker(https://www.docker.com/products/docker-desktop)

## How To Use

To clone and run this application, you'll need [Git](https://git-scm.com), [Maven](https://maven.apache.org/), [Java 11](https://www.oracle.com/technetwork/java/javase/downloads/jdk11-downloads-5066655.html). From your command line:

```bash
# To build the code docker image, open a command-line 
# window and execute the following command from parent project directory:
$ mvn clean package dockerfile:build

# Now we are going to use docker-compose to start the actual image.  To start the docker image, Run the following command from parent project directory: 
$ docker-compose -f docker/docker-compose.yml up
```

# The build command

Will execute the [Spotify dockerfile plugin](https://github.com/spotify/dockerfile-maven) defined in the pom.xml file.  

This is the first chapter we will have multiple Spring projects that need to be be built and compiled.
Running the above command at the root of the project directory will build all of the projects.
If everything builds successfully you should see a message indicating that the build was successful.

# The Run command

This command will run our services using the docker-compose.yml file located in the /docker directory.
If everything starts correctly you should see a bunch of Spring Boot information fly by on standard out.  
At this point all of the services needed for the chapter code examples will be running.

# Database - Connect to Postgres running inside Docker
You can find the database script as well in the docker directory.
```bash
docker container ls
docker exec -it CONTAINER_ID bash
psql -U postgres
\c databasename
\dt
```
