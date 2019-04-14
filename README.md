# Docker + Flask Tutorial

*Tutorial by: Madalyn Marabella*

This tutorial will show you how to create a simple flask app using Docker. Docker is a tool for creating and coordinating containers.

### Vocabulary
* **Image**: text
* **Container**: text
* **Dockerfile**: text

### Verify installation
```
$ docker run hello-world
```
You should receive the message:
```
Hello from Docker!
This message shows that your installation appears to be working correctly.
```

### Build and run image

The `docker build` command uses the dockerfile to create a docker **image**, which is a template for building docker **containers**.
```
$ docker build -t flask-simple:0.1 .
```

Using the specifications in the docker image, `docker run` creates a docker **container** (an isolated environment) and runs a series of instructions inside. One of the specifications in the dockerfile is `RUN pip install -r requirements.txt`, so the container built by `docker run` will have Flask installed. Then docker runs the command specified in the dockerfile. Our dockerfile has an `ENTRYPOINT` of "python" and the `COMMAND` "app.py", so it will run `python app.py` inside the container, which starts the Flask server.
```
$ docker run -p 5000:5000 flask-simple:0.1
```
