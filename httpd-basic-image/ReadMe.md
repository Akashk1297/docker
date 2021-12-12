# Build image
docker build -t httpd-basic-image:latest .

# Create Container
docker run -publish --8080:80 --detach name httpd-basic-container httpd-basic-image:latest

# Enter inside new container
docker exec -it httpd-basic-container /bin/bash
