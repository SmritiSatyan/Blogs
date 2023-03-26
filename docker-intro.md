## Docker

Most of us have come across terms like ‘Docker image’, ‘Docker daemon’ during application development. 

Docker resolves the conversation that reads “Oh, it worked on my machine, not sure why it isn’t working on yours. Have you resolved all the dependencies?”. 

### What is it?
Docker is an open-source platform that creates isolated environments and provides scalability for applications that don’t share resources. It also helps create, deploy and run applications inside Docker containers. Docker containers work on any OS-compatible host (Linux or Windows) provided Docker runtime is installed.

Containers are light-weight entities that contain all the resources (application code, libraries, dependencies, configuration files, system tools) necessary to run an application and ship it as a single package.

Docker constitutes of:
- Docker daemon that helps build, run, and manage containers.
- A high-level API for the user to communicate with the Daemon.
- A CLI to access and use the daemon, and API.

### Why Would You Use It?
Docker is a highlight during deployment. When we deploy code (developed in a local environment) into a production environment, Docker ensures that the code will work in this environment. 
It is guaranteed that the code tested locally is the same exact build artifact that goes into production. No changes are required in the application runtime environment. 

Multiple containers can run in the same environment and it gets efficient when the number of containers increases in the single Docker engine.

Docker wraps up an application such that deployment and runtime issues are handled outside the application, demonstrating consistency across containerized applications. 

Since it is open-source, anyone can contribute and customize it to their needs. This way, developers can focus on writing efficient code rather than worrying about the systems on which this code would run.

### What Impact Does It Have on the Development Ecosystem?
- Use system resources efficiently: They use less memory and consume fewer system instances to run the same workload.
- Consumes less time to deliver results: Technology is ever-changing. It is essential to scale and add new features as per business needs. Docker makes it easy to place software in production, provides software versioning, and helps transition between versions. 
- Enables application portability: Docker encapsulates the requirements of an application, hence supporting applications to move back and forth between different environments. When Docker runtime is installed, the application can run a Docker container on any instance of the OS.
- Instant start and stop: Docker can be started and stopped instantaneously. 
- Reallocates free memory: Free memory can be reallocated so that it can be reused across other containers within the Docker environment.
- Lightweight, and self-contained: Ensures that developers don’t work on solving tomorrow’s problems with yesterday’s development methods. This means Docker helps build future-ready software.
- Easy-to-use: It is easy to set up a local development environment with Docker without duplicating the resources. 
- Modular: It is easy to run multiple instances/versions of the same code without worrying about configuration and port issues. 

### Conclusion
Using a Docker container during all stages of application development is preferred since it validates the progress made in the development environment and production environment.

Docker is an exceptional tool that supports building an application from the development phase through the production phase.

Docker makes it easy to work with microservices too since they consist of loosely coupled components, where each component can be developed separately.

It takes a mind-shift and a small learning curve to fully adopt and adapt to Docker, and once this is done, there is no stopping from building a portable, scalable, ‘works-on-every-machine’ application.

### References

https://www.infoworld.com/article/3310941/why-you-should-use-docker-and-containers.html
https://stackoverflow.com/questions/45177473/docker-container-does-not-need-an-os-but-each-container-has-one-why
https://stackoverflow.com/questions/16047306/how-is-docker-different-from-a-virtual-machine
https://medium.com/uptime-99/the-benefits-of-using-docker-for-development-and-operations-2c5256ad89bc

