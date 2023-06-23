# Docker study
This is a proof of concept for a dockerized application.

## Dependencies
- [Docker](https://www.docker.com/)
- Linux or [WSL](https://docs.microsoft.com/en-us/windows/wsl/install-win10)

## Installation
1. Clone the repository
2. Execute `docker build -t mysql-image -f api/db/Dockerfile .` to build the mysql image
> - The `-t` flag is to tag the image with the name `mysql-image`
> - The `-f` flag is to specify the Dockerfile to use
> - The `.` is to specify the context of the build, in this case the current directory

> - To see the image execute `docker images`

## Create the container
1. Execute `docker run -d --rm --name mysql-container mysql-image` to create the container
> - The `-d` flag is to run the container in the background
> - The `--rm` flag is to remove the container when it exits
> - The `--name` flag is to specify the name of the container
> - The `mysql-image` is the name of the image to use
> - To see the containers execute `docker ps -a`
> - **If something goes wrong, execute `reboot`, works everytime**

## Create the database
1. Execute `docker exec -i mysql-container mysql -u root -p secret < api/db/database.sql` to create the database
> - The `-i` flag is to keep STDIN open even if not attached
