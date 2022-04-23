<!-- About The Project -->
# Data Analytic Setup using Docker & Portainer
This setup is a base data analysis/engineering setup, where its simplifies the process of setting up new development environment to start with using docker and portainer.

<!-- Used Container Images -->
### Containers (Docker & Docker Compose) Images:
- <a href="https://hub.docker.com/r/portainer/portainer-ce">Portainer</a>, <a href="https://hub.docker.com/r/jupyter/datascience-notebook">JupyterLab</a>
- <a href="https://hub.docker.com/_/postgres">PostgreSQL</a>, <a href="https://hub.docker.com/r/dpage/pgadmin4">pgAdmin</a>
- <a href="https://hub.docker.com/r/bitnami/minio">MinIO</a>, <a href="https://hub.docker.com/r/tylerfowler/superset">Superset</a>


### Setting Up Portainer:

Portainer allows you to manage your Docker stacks, containers, images, volumes, networks and more. It is compatible with the standalone Docker engine and with Docker Swarm. To run portainer using docker use the bellow command:


```
Port: 9443
Name: portainer_managment
Restart: always
Volume: portainer_data:/data
Image: portainer/portainer-ce:latest
```

Run the following command for spinning up portainer on docker container:

``` docker
docker run -d -p 9443:9443 --name portainer_managment --restart=always -v /var/run/docker.sock:/var/run/docker.sock -v portainer_data:/data portainer/portainer-ce:latest
```
After running the command above, you can reach portainer locally on port 9443 ( `localhost:9443` ) :

![Portainer Dashboard](img/portainer-1.png?raw=true "Portainer Dashboard")

### Setting Up Our Stack:

Our data analytic stack contains all needed tools to start with, including `JupyterLab`, `MinIO`, `PostgreSQL`, `PgAdmin` and `Apache Superset`. Used Jupyter as my analytic editor for my scripts, minIO as storage for my csv's files etc., postgres as my database of choice and pgAdmin as my adminstration gui for my database, and apache superset as my visualization tool of choice. 


Lets start deploying our stack by filling the following requirements:
- `Name`: Here were you declare the name of your stack
- `Build Method`: Here you choose how you prefer to build your stack, for me i have already prepared a docker-compose.yml file to use, so am gonna choose Upload method
- `Environment Variables`: Here were you can declare environment variables, for me am gonna deploy my prepared .env file

![Portainer Dashboard](img/portainer-2.png?raw=true "Portainer Dashboard")

After deploying the stack successfully, our stack is ready to use in the following ports:

- JupyterLab: ( `localhost:8888` )
- MinIO: ( `localhost:9000` or `localhost:9001` )
- PostgreSQL: ( `localhost:5432` ), PgAdmin: ( `localhost:5556` )
- Superset: ( `localhost:8088` )

![Portainer Dashboard](img/portainer-3.png?raw=true "Portainer Dashboard")
