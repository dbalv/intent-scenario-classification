# Environment

According to modern architecture-as-code standards, the environment is based on:

  * Docker https://docs.docker.com/engine/docker-overview/
  * Docker-Compose https://docs.docker.com/compose/
  * Conda https://conda.io/en/latest/
  
This allows you to have a single compatible version of the environment and avoid dependency problems during software installations. The environment is based on a single master component on top of which multiple conda virtual environments can run based on both Python and R kernels. 

You can interact with the environments through traditional IDEs based on Visual Studio Code, PyCharm and Eclipse by directly modifying the source code or through modern features based on remote development inside the Docker containers (see https://code.visualstudio.com/docs/remote/containers). Furthermore, it's possible to use the popular Jupyter Notebook web IDE also in its Jupyter Lab version at http://localhost:8888/tree or http://localhost:8888/lab. TensorBoard is still available at http://localhost:6006.

## System

### Prerequisites

The system needs Windows 10 Pro, Mac OS or a recent Linux distribution (tested on Windows 10 Pro). Docker, in its Docker Compose version must be installed.

  * Docker https://docs.docker.com/install/ 
  * Docker-Compose https://docs.docker.com/compose/install/
  
### Basic commands for installation

Build the docker images and setup local containers:

    $ docker-compose -f local.yml build
    $ docker-compose -f local.yml up
    
Test the environment configuration in a new CLI: 

    $ docker exec -it pde-master python -c 'import sys; print(sys.version)' 

### Environment Layout

The project layout follows the present scheme:

| Directory | Function |
| ------ | ------ |
|/.env|Environment variables needed by the Docker containers|
|/compose|Dockerfiles needed to create custom Docker images|
|/config|Configuration files for Docker microservices|
|/data|Any kind of data, from raw data to third party sources|
|/docs|Project documentation|
|/model|Trained and serialized models, model predictions, or model summaries|
|/notebook|Jupyter Notebooks|
|/src|Source code for use in the project|
|/test|Unit, integration, UI, infrastructure and performance tests|
