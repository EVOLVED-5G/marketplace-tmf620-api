# Swagger generated server 2.3.1

## Overview
This server was generated by the [swagger-codegen](https://github.com/swagger-api/swagger-codegen) project.  By using the [OpenAPI-Spec](https://github.com/OAI/OpenAPI-Specification) from a remote server, you can easily generate a server stub.

Upload product-catalog-management

### Upload the Server to Bluemix with client

1) cf login:
  cf login [-a API_URL] [-u USERNAME] [-p PASSWORD] [-o ORG] [-s SPACE]
  For Example:
  cf login -a https://api.ng.bluemix.net -u your@email.com -o tmforum -s apidev


2) cf push:
  cf push

### Local Use

1) start local mongoDB (or change /service/config.json file for external mongoDB)

2) npm start

Check out Description in Confluence:
https://projects.tmforum.org/wiki/pages/viewpage.action?pageId=38142767

This project leverages the mega-awesome [swagger-tools](https://github.com/apigee-127/swagger-tools) middleware which does most all the work.

## Deployment with Docker

Since this docker infrastructure connects to an external network, we need to create this network,
if it doesn't exist already. In order to create it, run:

```bash
docker network create docker_evolved5g_net
```

In order to build and launch the docker image and container, run:

```bash
docker build -t tmf_backend:latest .
```

```bash
docker run --name tmf_backend_container --rm 
--add-host=host.docker.internal:host-gateway -p 8080:8080 tmf_backend:latest
```

You can achieve this also by using docker compose. So run 

```bash
docker-compose up --build -d
```

In order to run the containers.