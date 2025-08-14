# Goenvshell

This repository contains a **Dockerfile** for building a Docker image with a ready-to-use Go development environment.
The environment includes:  

- **Architecture:** `linux/amd64`
- [protobuf-compiler](https://protobuf.dev/installation/)
- Protobuf plugins for Go:
  - [protoc-gen-go](https://pkg.go.dev/google.golang.org/protobuf/cmd/protoc-gen-go)
  - [protoc-gen-go-grpc](https://pkg.go.dev/google.golang.org/grpc/cmd/protoc-gen-go-grpc)

---

## 🚀 Build the Goenvshell Docker Image

Make sure [Docker](https://docs.docker.com/get-docker/) is installed on your system, then run:

```bash
docker build -t goenvshell .
```

---

## 🛠 Using Goenvshell

To run a container with your local Go project mounted:

```bash
export YOUR_GO_MODULE_PATH=/Users/user/example_go_module
docker run --rm -it   -v $YOUR_GO_MODULE_PATH:/go/src/app   -w /go/src/app   goenvshell bash
```

This will:

- Start the container using the `goenvshell` image
- Mount your Go project directory into `/go/src/app` inside the container
- Set the working directory to `/go/src/app`
- **Open a `bash` shell ready for development**
