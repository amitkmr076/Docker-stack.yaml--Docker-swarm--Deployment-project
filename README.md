Pre-requisite : follow this blog for step by step guide.
Blog : https://amitblog.hashnode.dev/mastering-docker-swarm-and-cluster-a-guide-to-multi-container-deployment-with-docker-cluster-and-beyond


Yaml file syntax Explanation -

1-  version: '3.7'
    This is the version of the Docker Compose file format that this YAML file uses. In this case, it's version 3.7.

2- services:
   This is the start of the services section, which defines the Docker containers that will be run by Docker Compose.

3-  django-app:
    image: amitkmr076/react_django_demo_app:latest
    ports:
      - "8000:8000"
   This defines a Docker container called django-app. It uses the Docker image amitkmr076/react_django_demo_app:latest, which is the latest version of a pre-built Docker image for running a Django web application. The ports section maps port 8000 inside the container to port 8000 on the host machine. This allows the Django web application to be accessed from the host machine's web browser at http://localhost:8000.

4-  mysql-db:
    image: mysql:latest
    ports:
      - "3306:3306"
    environment:
      MYSQL_ROOT_PASSWORD: test@123
This defines a Docker container called mysql-db. It uses the mysql:latest Docker image, which is the latest version of a pre-built Docker image for 
running a MySQL database. The ports section maps port 3306 inside the container to port 3306 on the host machine. This allows external applications 
to connect to the MySQL database running inside the container. The environment section sets the MYSQL_ROOT_PASSWORD environment variable to test@123.
This is the password that will be used to log in to the MySQL root account inside the container.

Overall, this YAML file defines two Docker containers that can be run together using Docker Stack or cluster: a Django web application running in one 
container,and a MySQL database running in another container. The containers are pre-configured with the necessary settings to allow them to communicate 
with each other and with external applications.

NOTE: Docker-compose and Docker-stack yaml file looks the same beacuse its basically a ddcoker-compose file but it applies on Docker-Swarm service.
we can say that Docker-Stack is an advance version of Docker-compose.
