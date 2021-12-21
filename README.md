### How to deploy a static HTML website from scratch with Docker and Ngnix
1. Create a directory for html page (ex. first-html-image)
2. Create Dockerfile in root 
    $touch Dockerfile
   ```
   FROM nginx:latest
   COPY html-page /usr/share/nginx/html
   ```

> These lines of code represent the image we're going to use along with copying the contents of the current directory into the container.

### How to build docker

#### Build images
`docker build --tag first-app:latest . `
#### Show images
`docker images ls'`

#### Run container
`docker run --name first-app -p 8080:80 -d first-app:latest`

### Test the Port with cURL
`curl localhost:8080`