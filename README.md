<h3>Docker file for Faveo Helpdesk</h3>

With this Docker file you can build a Docker image for Faveo Helpdesk

<h3>How to use</h3>

Clone the repository. 

Make sure you have docker-compose installed on your server. 

Run the following command to start Faveo and mySQL image:

<code>docker-compose up -d</code>

Open you ip address for fininshing Faveo installation.

When asked about database config. Use the same credentials as in docker-compose.yml:

       MYSQL_ROOT_PASSWORD: faveo
       MYSQL_DATABASE: faveo
       MYSQL_USER: faveo
       MYSQL_PASSWORD: faveo

You can change the environment variables for database configuration.

<h3>To change the nginx config image for your server edit defaul.conf</h3>

After changing nginx config rebuild the image.

<code>docker build -it "repo_name" .</code>

Now start the server using your own local image by changing the docker-compose file with your repo name as image under faveo:

       faveo:
          image: repo_name

Contributing
--------------------------
Create your own fork of Faveo master repositoray and use <a href="https://github.com/nvie/gitflow">git-flow</a> to create a new feature. Once the feature is published in your fork, send a pull request to begin the conversation of integrating your new feature into Faveo.

Help
--------------------------
Visit the <a href="https://github.com/ladybirdweb/faveo-docker/issues">issue</a> page. And if you'd like professional help commercial support is available, email us through the <a href="http://www.faveohelpdesk.com/contact-us/">contact form</a>.
<h3>Documentation</h3>
https://docs.google.com/document/d/1l2QyGGtxSm1ta-2qCkw7A3G74UqUKSPi8fgBCblRbqA


<h3>Reference</h3>
- https://hub.docker.com/r/ladybirdweb/faveo-docker
- https://github.com/ladybirdweb/faveo-server-images
