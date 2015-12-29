<h3>Docker file for Faveo HELPDESK</h3>

With this Docker file you can build a Docker image for Faveo HELPDESK

<h3>How to use</h3>

This image build is based on the docker image of tutum-docker-php so it does not provide a mysql server. To use the image there are several ways.

<h3>Use a Remote Database host</h3>

run the image from the repository

docker run -d --name invoice-faveo -e "DATBASE_TYPE=mysql" -e "DATBASE_HOST=db" -e "DATBASE_NAME=faveo" -e "DATBASE_USER=faveo" -e "DATBASE_PASSWORD=faveo" -p 80:80 rollbrettler/invoice-ninja

These are the default environment variables. Change the values to your server credentials.

<h3>Use a docker mysql container</h3>

You first need to initialize the database container with a name.

docker run --name some-db-name -e MYSQL_ROOT_PASSWORD=root -P -d mysql

After that, you need to connect to your mysql container and execute the sql that is recommended by Faveo HELPDESK developers. You find a copy in this repository (database-setup.sql)

Now you can start your invoice docker container

docker run -d --name faveo-helpdesk --link some-db-name:db -p 80:80 ladybirdweb/faveo-helpdesk

Thats it your Faveo HELPDESK container is running.

<h3>How to build</h3>

1. Clone the whole repo to your local machine
2. update the submodules with git submodule foreach git pull
3. change the directory to invoice-ninja src cd faveo-helpdesk/faveo-helpdesk
4. install the dependencies of Faveo HELPDESK composer install and bower install
5. change back to root of repository cd ../../
6. use docker build to build the image docker build -t="faveo-helpdesk" faveo-helpdesk/

Your image is now ready to use on your local machine
