# Docker Calculator

This is an extremely simple Docker "app" that asks for two integers and prints their sum to the console.

Dockerfile contents:
```
FROM ubuntu:16.04

WORKDIR /dir

CMD printf "First integer: "; read -r num1; printf "Second integer: "; read -r num2; printf "Their sum is: "; echo $(($num1+$num2))
```