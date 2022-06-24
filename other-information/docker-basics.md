# Docker basics

### What’s docker? <a href="#h.6nphn0mhqdcc" id="h.6nphn0mhqdcc"></a>

Docker is an open platform for developing, shipping, and running applications. Docker enables separation of the applications from infrastructure and makes delivery quick for the product and the product’s upgrades. Use of docker significantly reduces the time required for dependency resolution.

Think of docker images provided by Signzy as an equivalent of deployable .war files from the Java world.

### Docker daemon & docker client <a href="#h.j1tcr3z4f848" id="h.j1tcr3z4f848"></a>

The Docker daemon ($ dockerd) listens for Docker API requests and manages Docker objects such as images, containers, networks, and volumes. A daemon can also communicate with other daemons to manage Docker services.

The Docker client ($ docker) is the primary way that many Docker users interact with Docker. When you use commands such as docker run, the client sends these commands to dockerd, which carries them out. The docker command uses the Docker API.

### Docker images <a href="#h.h8yh1fhhhsv8" id="h.h8yh1fhhhsv8"></a>

An image is a read-only template with instructions for creating a Docker container. Images are stored in the docker registry (repository) and pulled into the required servers for creating the docker containers.

### Docker containers <a href="#h.k1dxvihqk33m" id="h.k1dxvihqk33m"></a>

_Docker provides the ability to package and run an application in a loosely isolated environment called a container._ The isolation and security allows running many containers simultaneously on a given host. Containers are lightweight and contain everything needed to run the application, so you do not need to rely on what is currently installed on the host.

**A container is a runnable instance of an image.** You can create, start, stop, move, or delete a container using the Docker API or CLI. You can connect a container to one or more networks, attach storage to it, or even create a new image based on its current state.

A container is defined by its image as well as any configuration options you provide to it when you create or start it. When a container is removed, any changes to its state that are not stored in persistent storage disappear.

### Docker Repository (Docker registry) <a href="#h.okrxcla2rjd" id="h.okrxcla2rjd"></a>

A Docker registry stores Docker images. When you use the docker pull or docker run commands, the required images are pulled from your configured registry. When you use the docker push command, your image is pushed to your configured registry.
