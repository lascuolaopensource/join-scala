# Development environment example

We're using [Docker](docker.com) and docker-compose to develop and deploy Join in an easy and fast way.
In this document you'll find instructions for deploying Join in a development environment using these tools.
You probably might want to use this environment to edit frontend looks before [deploying](github.com/lascuolaopensource/join/prod/README.md).

## How to use

Make sure you've cloned the repository and `cd` into `join/dev`.

#### Install required software

In order to set up your environment correctly you should have these softwares installed on your machine:

- docker
- docker-compose
- node 8.12

You can use shell scripts in `join/dev` if you are on Debian/Ubuntu.

        ./install_docker.sh
        ./install_node.sh

#### Set environment

Make a copy `dev.env.example` named `.env`.

        `sudo cp prod.env.example .env`

#### Add names to your hosts file

You need to add a copule of hostnames to your hosts file in order to get container connected.
Open the file:

        `sudo nano /etc/hosts`

and add these lines:

        127.0.0.1       backend
        127.0.0.1       frontend
        127.0.0.1       admin-frontend

#### Bring it up

When you're ready you can take it up with:

        `docker-compose up`

If you get no problems you can visit it at

- Public Frontend - http://localhost:8080
- Admin Frontend - http://localhost:8081
- Backend - http://localhost:9000
- pgadmin - http://localhost:8082


