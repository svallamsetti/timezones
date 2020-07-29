# Requirements
   * [Docker](https://docs.docker.com/get-docker/)
   * [Docker Compose](https://docs.docker.com/compose/install/)

## Project setup
Once docker and docker compose are installed follow the below steps to spin this app.

**Steps:**

1. clone this repo `git clone https://github.com/svallamsetti/timezones.git`
2. `cd timezones`
3. `cd timezones-api` 
4. Run `git submodule update --init`
5. `cd ../timeszones-consumer-vue` 
6. Run `git submodule update --init`
7. `cd ..`
8. `docker-compose up -d`
> This step will take some time to download the images used in Docker image files. The Dockerfile will take care of installing all the required dependencies.
9. `docker-compose ps` should display the following output
    ```
    timezones_backend_1    python timezonesapp.py           Up      0.0.0.0:5001->5000/tcp
    timezones_frontend_1   docker-entrypoint.sh npm r ...   Up      0.0.0.0:8081->8080/tcp

    ```
10. Once the containers are up and running, the app can be accessed by visiting url http://127.0.0.1:8081
11. To execute commands in containers `docker-compose exec serviceName command`  ex: `docker-compose exec backend pytest`
12. To run all the unit tests `docker-compose exec backend pytest`
13. Swagger documentation can be accessed at  http://127.0.0.1:5001/swagger
14. API's can be accessed at  http://127.0.0.1:5001/api/timezones 
http://127.0.0.1:5001/api/timezones/{timezoneId}
15. To remove all containers `docker-compose down`

## Alternate Installation

Please follow the Readme.md instructions for individual projects
1. [TimezonesAPI-flask](https://github.com/svallamsetti/timezones-api/blob/master/README.md)
2. [Timezones-consumer-vue](https://github.com/svallamsetti/timeszones-consumer-vue/blob/master/README.md)