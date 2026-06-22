# Multi-threaded Web Server
Objective: Build a simple web server that can handle multiple client requests concurrently.

Description: A multi-threaded web server written in object-oriented C++ that uses TCP/IP sockets and POSIX threads to concurrently serve HTTP requests.

## Requirements

- C++
- CMake
- Python

```bash
# start CMake build
$ cmake -B build && cmake --build build

# install external API dependencies
$ cd api && pip install -r requirements.txt
```

Modify ```.env``` to change IP addresses, ports, the number of threads and cache capacity.

## Usage

```bash
# start web server
$ cd build && ./multithreaded-server

# start external API
$ cd api && flask run
```

```bash
# GET request
$ curl -i http://127.0.0.1:8080/index.html

# HEAD request
$ curl -I http://127.0.0.1:8080/index.html

# POST request
$ curl -X POST -d "username=John%20Doe" -H "Content-Type: application/x-www-form-urlencoded" -i http://127.0.0.1:8080/api/user
```

```main.cpp``` simulates concurrent usage of the web server by sending requests from multiple client objects. Once the server is running, navigating to [http://127.0.0.1:8080/index.html](http://127.0.0.1:8080/index.html) in a web browser would display the result of making requests to the server. The browser will initially request ```index.html``` and upon receipt it will notice the file contains references to a stylesheet, script and image, and will send additional requests for these.

### Credit
The original guide was written by Nicholas Matsakis and Aaron Turon and can be found [here](https://doc.rust-lang.org/book/ch20-00-final-project-a-web-server.html).

Hii Making Changes for testing an Application
