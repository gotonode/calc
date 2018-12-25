# Docker Calculator

This is an extremely simple **Docker** "app" that asks for two integers and prints their sum to the console.

Dockerfile contents:
```
FROM ubuntu:16.04

WORKDIR /dir

CMD printf "First integer: "; read -r num1; printf "Second integer: "; read -r num2; printf "Their sum is: "; echo $(($num1+$num2));
```

## How to build this image?
Run this command: `docker build -t calc .`

This will build the Docker image with the instructions from the Dockerfile. It'll get a tag of `calc`.

## How to run the built image, creating a Docker container?
Run this command: `docker run -it calc`

This will create a Docker container from the image called `calc`.

## Sample program flow
```
First integer: 128
Second integer: 128
Their sum is: 256
```
