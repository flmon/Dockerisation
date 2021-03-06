Note: To run the tutorial, we can run a docker image (docker run -dp 80:80 docker/getting-started)
or go to link: https://docs.docker.com/get-started/

This project is to show a 'Dockerisation' process

0) Get some code (Node.js todo list app)
1) Create docker file in same folder as package.json (Dockerfile)
2) run cmd to build docker image (root app folder)
docker build -t getting-started .

3) run cmd to execute image (-d = detached mode) (-p x:y = port mapping host (x) to container (y))
docker run -dp 3000:3000 getting-started

4) do some code modification and rebuild image (docker build -t getting-started .)
to stop a running image : docker stop <container id>
to see container (ids): docker ps
to delete container (must be stopped): docker rm <id>

5) We can share image on Docker Hub
==> login: docker login -u <user>
==> tag: docker tag getting-started <user>/getting-started
==> push: docker push <user>/getting-started

6) We can test image with 'Play with Docker'

7) Persisting data:
volume creation: docker volume create <volname>
puis start app with mount volume (volname=todo-db):
docker run -dp 3000:3000 -v todo-db:/etc/todos getting-started

8) Multi-container
we can run the app in a container and it will connect to a MySQL docker image
see cmd_docker.txt for commands to run

9) Using Docker Compose
a) create file docker-compose.yml (at app root)
b) define services in the YAML file
c) run docker-compose
docker-compose up -d




