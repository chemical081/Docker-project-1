<h1>Hosting a static website using nginx with Docker</h1>

<ul>
  <h2>Steps</h2>
  <li><h3>Dockerizing your website</h3>First step is to create a Dockerfile in the root directory of the project. This is the file that defines how the docker image should be built. The file should be named 'Dockerfile' and once it is done follow the following steps.</li>
  
  ```` Dockerfile
    FROM nginx:latest 
    COPY . /usr/share/nginx/html
  ````
  
  <li><h3>Build your Docker Image</h3></li>

  *Run the following command to build the image 

  ````Dockerfile
    docker build -t my-website
  ````
  <p>we are adding "-t" to name in our code to name the image. </br>If it's just for practice you can simply skip and just type "." which i have done in my code</p>

  <li><h3>To see wheather or not you have created a image or not you can simply type:</h3></li>
  
  ````Dockerfile
    docker images
  ````
This will list all the images that you currently have.
  
  <li><h3>Run your Docker Container</h3></li>
  After building our image, we can run a container based on this image. Copy the following code:

  ````Dockerfile
    docker run -d -p 8080:80 my-website
  ````
  This command runs the container in daemon mode "-d" and maps port "-p" 8080 on our host to port 80 inside the container.

  <li><h3>To see wheather you have the docker image running on a container you can simply type:</h3></li>

  ````Dockerfile
    docker ps
  ````
This will list all the images that are currntly running inside a container.
  
  <li><h3>Deploy in a localhost</h3></li>
  Now open your webbrowser and visit "https://localhost:8080" to see your static website hosted by nginx via Docker
</ul>
