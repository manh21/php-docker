# PHP Docker

Dockerize php project, this provide boilrplate for PHP in Docker and support for Traefik Reverse Proxy. Behind the scene this project use nginx to provide connection between external reverse proxy or connection to PHP FastCGI.

## Getting Started

### Configuration file
Contain config file for php and nginx inside `conf` folder.

### Folder permission
Allow docker to write, read, and excute files inside `src` folder. `chown -R 777 ./src`

### Traefik Labels
If you don't use Traefik as Reverse Proxy *REMOVE LABELS* and it's content inside `docker-compose.yml`.`

### Envoirement Variables
- HOSTNAME, only neeed when using Traefik.

### Prerequisites

Understanding how Docker and Reverse Proxy works. Has some experiance configure Docker, Nginx, and PHP.
