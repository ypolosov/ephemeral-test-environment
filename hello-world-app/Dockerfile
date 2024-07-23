FROM golang:latest AS builder
COPY ./hello-world.go .
RUN  go env -w CGO_ENABLED=0 GO111MODULE=off && go build -o /app/hello-world

FROM alpine:3.20.2
WORKDIR /app
COPY --from=builder /app/hello-world .
EXPOSE 8080
CMD ["./hello-world"]
