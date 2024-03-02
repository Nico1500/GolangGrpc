# Go gRPC Email Management Microservice

This Go project is a microservice designed to demonstrate the capabilities of gRPC (Google Remote Procedure Call) for building efficient, high-performance web services. It provides a simple email management system with CRUD (Create, Read, Update, Delete) operations, i use SQLite for storage. This service is ideal for learning how to implement gRPC services in Go and understanding the interaction between a Go server and a SQLite database.

## Features

- **CRUD Operations**: Manage email entries with create, read, update, and delete operations.
- **gRPC Implementation**: Utilizes gRPC for efficient communication between the client and server.
- **SQLite Database**: File-based database for easy setup and tear down.
- **Protobuf Definitions**: Use Protocol Buffers for defining service methods and message formats.

## Getting Started

### Prerequisites

- Go 1.22 or higher
- This project requires a `gcc` compiler installed and the `protobuf` code generation tools.
- Install the `protoc` tool using the instructions available at [https://grpc.io/docs/protoc-installation/](https://grpc.io/docs/protoc-installation/).

### Use

2. **Install Dependencies**

`go install google.golang.org/protobuf/cmd/protoc-gen-go@latest`

`go install google.golang.org/grpc/cmd/protoc-gen-go-grpc@latest`

    Compile the protobuf definitions and install Go dependencies.

    ```bash
    protoc --go_out=. --go_opt=paths=source_relative \
      --go-grpc_out=. --go-grpc_opt=paths=source_relative \
      proto/*.proto
    ```

    ```bash
    go mod tidy
    ```

3. **Run the Server**

    Start the gRPC server.

    ```bash
    go run ./server
    ```

4. **Run the Client**

    Execute client commands to interact with the server.

    ```bash
    go run ./client
    ```
## Usage

The microservice supports the following operations via gRPC calls:

- **CreateEmail**: Add a new email entry to the database.
- **GetEmail**: Retrieve an email entry by its address.
- **UpdateEmail**: Update an existing email entry.
- **DeleteEmail**: Remove an email entry from the database.
- **ListEmails**: List all email entries with pagination support.