# Docker

Docker is a tool that helps developers build, deploy, and run applications more easily. It does that by packaging an application and all it needs (libraries, code, system tools, etc.) into virtual containers. This allows you to quickly deploy applications into any environment containing Docker, and your code will run.

## Basic commands:

* Build containers from Dockerfile: `docker build . -t <name>`

* Run containers: `docker run <name>`

* If got a `docker-compose.yml` file: `docker-compose up`

* Show current Docker processes running: `docker ps`

* Show current Docker images: `docker images`

* Delete an image: `docker rmi <imageID>`

* Kill a container: `docker kill <imageID>`

---

More details in [my blog post](https://levelup.gitconnected.com/intro-to-docker-for-front-end-developers-22ed1942c4a5)
