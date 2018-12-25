# Docker Calculator

[![Codefresh build status]( https://g.codefresh.io/api/badges/pipeline/gotonode_marketplace/gotonode%2Fcalc%2Fcalc?branch=master&key=eyJhbGciOiJIUzI1NiJ9.NWMyMTM5NzM3NWVhMDExZjkxNjZhMzk3.injO-ZcBuCv9g009YPl22PkE7gSPEgXvi5zkL1P2JGw&type=cf-1)]( https://g.codefresh.io/pipelines/calc/builds?repoOwner=gotonode&repoName=calc&serviceName=gotonode%2Fcalc&filter=trigger:build~Build;branch:master;pipeline:5c2250a675a47582ef87b73c~calc)

This is an extremely simple **Docker** "app" that asks for two integers and prints their sum to the console.

Dockerfile contents (click [here](https://github.com/gotonode/calc/blob/master/Dockerfile) to view the file):
```
FROM ubuntu:16.04

WORKDIR /calc

CMD printf "First integer: "; read -r num1; printf "Second integer: "; read -r num2; printf "Their sum is: "; echo $(($num1+$num2));
```

## How to build this image?
Run this command: `docker build -t calc .`

You'll need to run this from the same directory that the Dockerfile is in.

This will build the Docker image with the instructions from the Dockerfile. It'll get a tag of `calc`.

## How to run the built image, creating a Docker container?
Run this command: `docker run -it calc`

This will create a Docker container from the image called `calc`.

Optionally pass the `--rm` argument to immediately remove the container once the calculation has been done.

## Sample program flow

Once a container has been created and you've gained console access to it (either by by using the `attach`-command or by passing the `-it` parameter), you can expect the program flow to look similar to the following:

```
First integer: 128
Second integer: 128
Their sum is: 256
```

You'll pass the two integers yourself as input and get their sum as output from the app.
