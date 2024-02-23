# Go Hello World Web Application - Print a beautiful ASCII octopus

This folder contains a basic web application in Go that displays an ASCII octopus when accessed by calling the exposed HTTP listener.

## Prerequisites

Make sure you have Go installed on your machine. You can download it from [here](https://golang.org/dl/).

## Getting Started

1. Clone the repository:

   ```bash
   git clone https://github.com/banshee86vr/ephemeral-test-environment.git
   cd hello-world-app
   ```

2. Compile the Go code:

   ```bash
   go build -o hello-world hello-world.go
   ```

3. Run the application:

   ```bash
   ./hello-world
   ```

   Open your web browser and go to [http://localhost:8080](http://localhost:8080). You should see a friendly ASCII octopus like this:

   ```text

                                               @@
                        @@@                    @
                       @   @@                   @@
                            @        @@@@         @@
                           @ @@@@  @@@@@@@@@       @@        @@
                        @@@.    (@@@@@@@@@@@      @@@      @    @
                        @@ @    @@@@@@@@@@@@     @@@       /    @/
            @@    @@    @@@     @@ @@@@@@@@   @@@@            @@
          &        @     @@@@@   @@@@@@@@.@@@@@@@@@@@@@@@@@
                 @@         @@@@@@@@@@@@@@@@@@@@@@@@@@@
                @@/          @@@@@@@@@@@@@@@@@@@@@  @@@@@@@
                 @@@@@#@@@@@@@@@@@@@@@@@@@@@   @@@@@@@    @@@
                     @@@@@    @@@@@.    @@@@@@@@     @@@   @@@   @@@@
                             @@@@(    @                @    @@.      @
                            @@@@     @@                @@     @@@  /@@
                            @@@     @@          @@     @@
                           @@@/    @@            @@    @
                            @@    @@                @@
                             @@@@
   ```

## Docker

Alternatively, you can use Docker to run the application in a container and deploy it on Kubernetes.

1. Build the Docker image:

   ```bash
   docker build -t hello-world .
   ```

2. Run the Docker container instance:

   ```bash
   docker run -p 8080:8080 hello-world
   ```

   Open your web browser and go to [http://localhost:8080](http://localhost:8080) to see the ASCII octopus.

## Cleanup

If you want to remove the Docker image and all related containers:

```bash
docker stop $(docker ps -aq --filter ancestor=hello-world)
docker rmi hello-world
```
