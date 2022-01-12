### How to deploy a PHP basic application scratch with Docker 
1. Create a directory (ex. php-demo)
2. Create Dockerfile in root 
    $touch Dockerfile
   ```yaml
    FROM php:8.0-apache ## Pull the image from dockerhub
    COPY index.php /var/www/html/index.php ## Copy file index.php to directory /var/www/html in image.
    EXPOSE 80 ## Port 80 is exposed for apache.
    CMD ["usr/sbin/apache2ctl", "-D", "FOREGROUND"] ## Apache started the container.
   ```

> These lines of code represent the image we're going to use along with copying the contents of the current directory into the container.

### How to build docker

#### Build images
`docker build -t php-demo:latest . `

#### Run container
`docker run --name first-php-app -p 9090:80 -d first-app:latest`

#### Show images
`docker images ls`

### Test the Port with cURL
`curl localhost:9090`
