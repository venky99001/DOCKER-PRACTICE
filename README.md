# 1. Check Docker version
docker --version

# 2. Docker system info
docker info

# 3. Check image history
docker history httpd

# 4. Pull image from Docker Hub
docker pull httpd

# 5. List all images
docker images

# 6. Run basic container
docker run httpd

# 7. Run with command
docker run httpd echo "Hello World"

# 8. Run with name
docker run --name my-container httpd

# 9. Run in interactive mode
docker run -it ubuntu bash

# 10. Run in background
docker run -d httpd

# 11. Run with port mapping
docker run -p 8080:80 nginx

# 12. Run with environment variable
docker run -e MY_VAR=value httpd env

# 13. Run with multiple environment variables
docker run -e APP_ENV=production -e VERSION=1.0 nginx

# 14. Run Ubuntu with env variable
docker run -it -e MY_NAME=John ubuntu bash

# 15. Check env inside container
echo $MY_NAME

# 16. Pass environment variable from host (Linux)
export APP_PORT=8080
docker run -e APP_PORT=$APP_PORT nginx

# 17. Using .env file
docker run --env-file .env nginx

# 18. Run with interactive + background
docker run -it -d httpd

# 19. List running containers
docker ps

# 20. List all containers
docker ps -a

# 21. Execute inside container
docker exec -it <container_id> bash

# 22. Remove container
docker rm <container_id>

# 23. Remove image
docker rmi <image_id>

# 24. Force remove image
docker rmi -f <image_id>

# 25. MongoDB container example
docker pull mongo
docker run -d --name DB-app -p 80:8082 mongo

# 26. Apache container example
docker pull httpd
docker run -d --name my-apache -p 8080:80 httpd

# 27. Modify HTML inside container
docker exec -it my-apache bash
echo "<h1>Hello from Docker</h1>" > /usr/local/apache2/htdocs/index.html

# 28. Test output
curl http://localhost:8080

# 29. Run with volume + env + name
docker run -it --name my_app -e APP_ENV=production -v C:\app\data:/data ubuntu /bin/bash
