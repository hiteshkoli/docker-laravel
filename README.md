# Docker for Laravel

A very simple docker setup for Laravel local development.

### Prerequisites

To get started, make sure you have [Docker installed](https://docs.docker.com/docker-for-mac/install/) on your system, and then clone this repository.

### Usage

First add your entire Laravel project to the `src` folder, then open a terminal and from this cloned repository's root run `docker-compose up -d --build`. Open up your browser of choice to [http://localhost:8080](http://localhost:8080) and you should see your Laravel app running as intended. 

**NOTE: Your Laravel app needs to be in the src directory first before bringing the containers up, otherwise the artisan container will not build, as it's missing the appropriate file.**  

Containers those are created and their ports are as follows:

- **nginx** - `:8080`
- **mysql** - `:3306`
- **php** - `:9000` 

 

### Persistent MySQL Storage


By default, whenever you bring down the docker-compose network, your MySQL data will be removed after the containers are destroyed. If you would like to have persistent data that remains after bringing containers down and back up, do the following:

- Under the mysql service in your `docker-compose.yml` file, add the following lines:

```
volumes:
  - ./mysql:/var/lib/mysql
```
 
## License

This project is licensed under the GNU General Public License v3.0 - see the [LICENSE](LICENSE) file for details