# Container Images Repository for TechPrimers
All TechPrimer DockerImages/NPM Packages/Maven artifacts can be viewed under "packages" tab

If you need to access these images for your deployments.
Use this token - `524ea08fef8c273c2f739920a8427b502f7dc789`

## Commands Used
### Create docker images using `build`
- `docker build . -t containers-demo:v1`

### Tag the images to the package registry path
- `docker tag containers-demo:v1 docker.pkg.github.com/techprimers/container-images/containers-demo:v1`

### Run the docker image on the engine
- `docker run containers-demo:v1 -p 8080:8080`

### Push the images to the Github package registry
- `docker push docker.pkg.github.com/techprimers/container-images/containers-demo:v1`

### Dockerfile
```
FROM openjdk:8-jdk-alpine
COPY target/containers-demo.jar containers-demo.jar
EXPOSE 8080
ENTRYPOINT ["java","-Djava.security.egd=file:/dev/./urandom", "-jar", "containers-demo.jar"]
```

### Other commands
- `docker images`
- `docker ps -a`
