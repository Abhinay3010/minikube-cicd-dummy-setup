FROM golang:1.17-alpine AS builder
WORKDIR /app
COPY main.go .
RUN go mod init app3 || true # Initialize module if not already
RUN go build -o /app3 main.go

FROM alpine:latest
WORKDIR /root/
COPY --from=builder /app3 .
EXPOSE 80
CMD ["./app3"]
