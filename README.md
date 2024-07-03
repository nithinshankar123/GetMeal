# GetMeal


```markdown
# GetMeal Project - Dockerized Web Application

This project demonstrates how to containerize a simple web application using Docker. The web application consists of HTML and CSS files and is served using Nginx. The Docker image is built and pushed to Docker Hub for easy access and deployment.

## Steps to Containerize and Deploy the Web Application

### 1. Clone the Repository
First, clone the repository containing the HTML and CSS files.

```sh
git clone https://github.com/nithinshankar123/GetMeal.git
cd GetMeal
```

### 2. Create and Write the Dockerfile
Create a Dockerfile in the project directory. This Dockerfile will define how to build the Docker image.

```sh
touch Dockerfile
nano Dockerfile
```

Add the following content to the `Dockerfile`:

```Dockerfile
# Use the official Nginx image from the Docker Hub
FROM nginx:alpine

# Copy HTML files to the default Nginx html directory
COPY *.html /usr/share/nginx/html/

# Copy CSS files to the default Nginx html directory
COPY *.css /usr/share/nginx/html/

# Expose port 80 to be able to access the web server
EXPOSE 80

# Start Nginx when the container launches
CMD ["nginx", "-g", "daemon off;"]
```

### 3. Build the Docker Image
Build the Docker image locally using the Dockerfile.

```sh
docker build -t getmeal-image .
```

### 4. Log in to Docker Hub
Log in to your Docker Hub account to be able to push the image.

```sh
docker login
```

### 5. Tag the Docker Image
Tag the Docker image in a format that Docker Hub understands. Replace `your-username` with your Docker Hub username.

```sh
docker tag getmeal-image your-username/getmeal-image:latest
```

### 6. Push the Docker Image to Docker Hub
Push the tagged Docker image to Docker Hub.

```sh
docker push your-username/getmeal-image:latest
```

### 7. Run the Docker Container
Run the Docker container to serve the web application using Nginx. This maps port 80 of the container to port 80 of the host machine.

```sh
docker run -d -p 80:80 --name getmeal-container getmeal-image
```
###Pulling my Image
```sh
docker pull nithin272/getmeal-image:latest
```

## Summary
- Cloned the `GetMeal` repository from GitHub.
- Created a Dockerfile to use the official Nginx image and copy the HTML and CSS files to the appropriate directory.
- Built a Docker image locally.
- Logged in to Docker Hub and tagged the Docker image.
- Pushed the Docker image to Docker Hub.
- Ran the Docker container to serve the web application.


The Docker image is now available on Docker Hub: [GetMeal Docker Image](https://hub.docker.com/repository/docker/nithin272/getmeal-image)

This project was a fantastic learning experience in working with Docker and deploying web applications. Thank you to everyone who has supported me along this journey!

#Docker #GitHub #CloudComputing #WebDevelopment #Nginx #DockerHub #Containerization #DevOps
```

Feel free to customize this README content to better fit your project and personal style.
