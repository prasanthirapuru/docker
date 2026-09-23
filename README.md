# Docker — Interview Q&A

### 1. What is Docker?

"Docker is a containerization platform used to package an application along with its dependencies and required environment into a container. This allows the application to run consistently across different environments, such as a developer's machine, testing environment, and production server."

### 2. What is a Dockerfile?

"A Dockerfile is a text file containing instructions for building a Docker image. It specifies things like the base image, dependencies, application files, working directory, and the command required to start the application."

### 3. What is a Docker image?

"A Docker image is a packaged, read-only template containing an application, its dependencies, and the filesystem required to create a container. The image is built using a Dockerfile."

### 4. What is a Docker container?

"A Docker container is a running instance of a Docker image. It provides an isolated environment where the application and its processes actually run."

### 5. What is the relationship between Dockerfile, image, and container?

"First, we define the application environment in a Dockerfile. Docker uses that Dockerfile to build an image. The image contains the application and its dependencies. When we run the image, Docker creates a container, which is the isolated environment where our application actually runs."

### 6. What are environment variables?

"Environment variables are used to provide configuration to an application from outside the application code. They allow us to use different configurations in development, testing, and production without modifying the application code. They can also be used for values such as database URLs and secrets."

### 7. Why don't we normally use localhost for container-to-container communication?

"We don't normally use localhost for container-to-container communication because localhost inside a container refers to that same container. Docker Compose provides a network where services can communicate using their service names. For example, the frontend container can communicate with the backend using `http://backend:8000`."

### 8. Why do we use Docker?

"We use Docker to make the application environment consistent and reproducible. Instead of manually installing and configuring all the required dependencies and services on every machine, we can define the environment using Dockerfiles and Docker Compose. This makes development, testing, and deployment easier and reduces environment-related problems."

### 9. How did you use Docker in your project?

"I used Docker to containerize my frontend and backend applications. I created a Dockerfile for each application, which contains the instructions required to build its Docker image. The Docker image packages the application and its dependencies, and when the image is run, Docker creates a container where the application actually runs. I used Docker Compose to manage both the frontend and backend services together. I also used environment variables to provide configuration such as the database URL and other settings without hardcoding them in the application code. For networking, containers can communicate with each other using Docker Compose service names, such as `backend:8000`, because localhost inside a container refers to that container itself. In my frontend configuration, `localhost:8000` is used because the API request is made by the browser on the host machine, and Docker maps the host's port 8000 to the backend container.
