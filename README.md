# TELENOT_NODEJS
Program to read the states for several contacts from a Telenot alarm system using the GMS-Protcol.

## Idea
As the Telenot KNX Gateway is quite expensive, I started research for another solution. Some people already got a solution working for Loxone, which I took as a reference. Then I started to implement a solution in Python which was working but caused high CPU usage running as a docker container (see python branch). So I decided to implement it in Javascript using node.js. This is my first Javascript project so it might not follow best practices. I'm welcome for tips / best-practices.

## Implementation

## Run
You can either run the program using your local node.ja version or run it using docker. For Docker you need to build the docker image using
    docker build -t michelmu/telenot-nodejs .
afterwards you can start the container using 
    docker run -p 49160:8080 -e LOG_LEVEL="info" --name telenot-nodejs --restart=always -d michelmu/telenot-nodejs
Posible log levels are ["error", "warn", "info", "verbose", "debug", "silly"]

## Hardware
To get the serial data to the ethernet bus I use the following converter: USR-TCP232-302 Tiny - RS232 to Ethernet TCP-IP-Server-Modul (ordered at Amazon). In my program I can connect to this module using a socket connection and get the data.

## To-Do's
- setup Mocha as Test Framework