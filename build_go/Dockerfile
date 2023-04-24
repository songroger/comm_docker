# Choose the base image for building the Go application
FROM golang:1.19 AS builder

# Set the working directory
WORKDIR /app

# Copy the Go module files
COPY go.mod go.sum ./

# Download the dependencies
RUN go mod download

# Copy the application files
COPY . .

# Build the Go application
RUN go build -o /go-docker-app

# Create a lightweight final image
FROM alpine:latest

# Copy the built Go application from the builder stage
COPY --from=builder /go-docker-app /go-docker-app

# Set the entrypoint for the container
ENTRYPOINT ["/go-docker-app"]