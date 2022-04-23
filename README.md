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

``` docker
docker run -d -p 9443:9443 --name portainer_managment --restart=always -v /var/run/docker.sock:/var/run/docker.sock -v portainer_data:/data portainer/portainer-ce:latest
```

After running the command above, you can reach portainer locally on port 9443 (localhost:9443) :

![Portainer Dashboard](img/portainer-1.png?raw=true "Portainer Dashboard")

### Setting Up Our Stack:

Our data analytic stack contains all needed tools to start with, including JupyterLab, MinIO, PostgreSQL, PgAdmin and Apache Superset. Used Jupyter as my analytic editor for my scripts, minIO as storage for my csv's files etc., postgreSQL as my database of choice and pgAdmin as my adminstration gui for my database, and apache superset as my visualization tool of choice. 